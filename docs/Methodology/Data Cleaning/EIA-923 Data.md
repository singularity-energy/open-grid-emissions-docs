---
stoplight-id: cleaning_eia923
---

Steps

* EIA-923: [https://catalystcoop-pudl.readthedocs.io/en/latest/data_sources/eia923.html#notable-irregularities](https://catalystcoop-pudl.readthedocs.io/en/latest/data_sources/eia923.html#notable-irregularities) 
    * EIA-860 / Boiler-Generator Association: [https://catalystcoop-pudl.readthedocs.io/en/latest/data_sources/eia860.html#notable-irregularities](https://catalystcoop-pudl.readthedocs.io/en/latest/data_sources/eia860.html#notable-irregularities) 

1. Generation and fuel allocation
2. Update energy source codes
    1. Validation: Ensure no missing ESC
3. Determine primary fuel
4. Calculate emissions from fuel consumption
5. Calculate biomass-adjusted emissions
6. Calculate CHP-adjusted emissions
7. Calculate CO2e
8. Aggregate the data by generator
9. Remove certain plants
10. Add subplant ID and prime mover code


## Allocating Generation and Fuel Data

The EIA-923 dataset reports net generation and fuel consumption data in three different tables, as summarized in the below table.

<table>
  <tr>
   <td>Table Name / abbreviation
   </td>
   <td>Aggregation level
   </td>
   <td>Required reporters
   </td>
   <td>Data reported
   </td>
  </tr>
  <tr>
   <td>Generation and fuel (GF)
   </td>
   <td>Prime-mover / fuel
   </td>
   <td>Any grid-connected plant >1MW nameplate capacity
   </td>
   <td>Monthly net generation and fuel consumption (separated by total and consumed for electricity generation)
   </td>
  </tr>
  <tr>
   <td>Boiler Fuel (BF)
   </td>
   <td>Boiler ID / fuel
   </td>
   <td rowspan="2" >Only units with steam turbines (ST) driven by steam from a boiler fueled by combustible fuels. Mostly consists of units > 10MW.
   </td>
   <td>Monthly fuel consumption totals
   </td>
  </tr>
  <tr>
   <td>Generator (G)
   </td>
   <td>Generator ID
   </td>
   <td>Monthly net generation totals
   </td>
  </tr>
</table>




Because different plants (and parts of plants) report to different tables at different aggregations, the generation and fuel data reported in one table does not always match the generation and fuel data reported in another. Although the GF table is more complete, the BF and G tables are more granular. 

Thus, the data pipeline distributes the complete data from the GF table (at the prime mover level) to the generator level using data reported in the G and BF tables, as well as using data from other EIA tables. The allocation process assumes that:
* The GF table is the authoritative source of information about how much generation and fuel consumption is attributable to an entire plant.
* The G table is the authoritative source of information about how much generation is attributable to an individual generator, if it reports in that table.
* The BF table is the authoritative source of information about how much fuel consumption is attributable to an individual boiler, if it reports in that table.

Net generation data from the GF table is allocated to individual generators proportionally to the the reported generation data for each generator in the G table, if available, and otherwise is allocated proportionally to the nameplate capacity of each generator with the same fuel type and prime mover. Likewise, fuel consumption data from the GF table is allocated to individual generators proportionally to the the reported fuel consumption data for each boiler in the BF table, if available, and otherwise is allocated proportionally to the nameplate capacity of each generator with the same fuel type and prime mover. 

Because fuel consumption in the boiler_fuel_eia923 table is reported per `boiler_id`, we must first map this data to generators using the Boiler-Generator Association table from EIA-860. For boilers that have a 1:m or m:m relationship with generators, we allocate the reported fuel to each associated generator based on the nameplate capacity of each generator. So if boiler "1" was associated with generator A (25 MW) and generator B (75 MW), 25% of the fuel consumption would be allocated to generator A and 75% would be allocated to generator B.
