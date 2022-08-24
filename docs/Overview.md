---
stoplight-id: 62rdm95g0apb6
---

# Summary of the Data

> This page is a work in progress.

## Files

The data is organized into three categories based on the primary use case



* **Carbon accounting data**: This will contain BA-level, _consumption-_based emission rates and fuel mix data. 
    * Intended user: This data is intended for those wishing to understand the source and emission intensity of the electricity they are consuming. 
    * File structure: data for each BA will be located in its own separate file.
* **Power sector data**: This will contain BA-level, _production_-based data on generation, emissions, and fuel consumption split out by fuel type. 
    * Intended user: This data is intended for analysts who seek to understand the operating characteristics of the power generation fleets in each region. 
    * File structure: data for each BA will be located in its own separate file
* **Power plant data**: This will contain plant-level data on hourly power plant operations and  static attributes of each plant. 
    * Intended user: This data is intended for researchers who seek to understand individual power plants, or who want to perform their own aggregations of the data. 
    * File structure: include all dynamic data in a single large csv (perhaps a tar.gz file) and all static attributes (e.g. fuel type, BA, etc) in a separate table, with the plant_id_eia as the primary key

Each of these data categories includes data at different temporal resolutions (hourly, monthly, annual), and in different units (U.S. and Metric). U.S.-unit files uses lb for mass and MMBtu for fuel consumption, while the metric files use kg for mass and GJ for fuel consumption. 


## Uses and Users


### Researchers 



* Any/all? But highlight the ways that we’ve included methodology info in the data, eg where the data came from, what shaping method was used, what GTN method was used


### Electricity users 



* Consumed data 


### Power grid operators 



* Generated BA-level and/or plant-level data


### Policy-makers 



* Generated and consumed data? Some policies (eg, RPS) act on generated electricity, however, policy-makers should also be informed about the actual consumed emissions in their regions 


## Input Data Sources

**EPA Continuous Emissions Monitoring System (CEMS) data**



* **What is it**: Measured hourly gross generation, fuel consumption, and emissions (CO2, NOx, SO2) data for emitting power generation units > 25MW
* **How we use it**: Primary source for hourly emissions and generation data
* **More information**: [https://ampd.epa.gov/ampd/](https://ampd.epa.gov/ampd/) 

**EIA Form 923**



* **What is it**: Reported monthly net generation and fuel consumption data for power generators > 1 MW
* **How we use it**: To convert gross generation data from CEMS to net generation, and to fill in generation and emissions data for generator-months that are not reported in CEMS
* **More information**: [https://www.eia.gov/electricity/data/eia923/](https://www.eia.gov/electricity/data/eia923/) 

**EIA Form 860**



* **What is it**: Inventory of all generators and plants and their static characteristics
* **How we use it**: to transform and aggregate the data reported in CEMS and EIA-923 based on plant and generator characteristics; calculating NOx and SO2 emissions based on plant-specific emissions control equipment and boiler types
* **More information**: [https://www.eia.gov/electricity/data/eia860/](https://www.eia.gov/electricity/data/eia860/) 

**EIA Form 861**



* **What is it**: Data about electric utility and power marketer sales and operations
* **How we use it**: Calculating grid gross loss based on utility disposition
* **More information**: [https://www.eia.gov/electricity/data/eia861/](https://www.eia.gov/electricity/data/eia861/) 

**Public Utility Data Liberation (PUDL) Project**



* **What is it**: an open source data processing pipeline that makes U.S. energy data easier to access and use programmatically
* **How we use it**: To access pre-cleaned and standardized versions of CEMS, EIA-923, and EIA-860 data
* **More information**: [https://catalystcoop-pudl.readthedocs.io/en/latest/](https://catalystcoop-pudl.readthedocs.io/en/latest/) 

**EPA-EIA Power Sector Data Crosswalk**



* **What is it**: Maps EPA plant IDs and unit IDs to EIA plant IDs and generator IDs
* **How we use it**: To crosswalk data between CEMS and EIA-923
* **More information**: [https://www.epa.gov/airmarkets/power-sector-data-crosswalk](https://www.epa.gov/airmarkets/power-sector-data-crosswalk) 

**EIA Form 930 / Hourly Electric Grid Monitor**



* **What is it**: Reported hourly net generation by fuel category, demand, and interchange for each Balancing Area in the U.S. 
* **How we use it**: To assign an hourly profile to the monthly generation and fuel data reported in EIA-923 and to calculate hourly consumed emission factors
* **More information**: [https://www.eia.gov/electricity/gridmonitor/about](https://www.eia.gov/electricity/gridmonitor/about) 

**EPA eGRID database**



* **What is it**: Reports annual-level generation and emissions statistics at the plant and BA level 
* **How we use it**: to validate our outputs, and as a source for certain static tables (emission factors, conversion factors, etc)
* **More information**: [https://www.epa.gov/egrid](https://www.epa.gov/egrid)


## Using the Code Repository


## A note on power plant terminology



* Boiler
* Generator
* Unit
* stack
* prime mover
* Plant

<table>
  <tr>
   <td>
Term
   </td>
   <td>Definition
   </td>
   <td>Used by
   </td>
   <td>
   </td>
  </tr>
  <tr>
   <td>Boiler
   </td>
   <td>Combusts fuel
   </td>
   <td>EIA
   </td>
   <td>
   </td>
  </tr>
  <tr>
   <td>Generator
   </td>
   <td>Produces electricity
   </td>
   <td>EIA
   </td>
   <td>
   </td>
  </tr>
  <tr>
   <td>Stack
   </td>
   <td>Exhausts emissions
   </td>
   <td>EPA
   </td>
   <td>
   </td>
  </tr>
  <tr>
   <td>Unit
   </td>
   <td>GRoup of boilers that are connected to the same stack
   </td>
   <td>EPA
   </td>
   <td>
   </td>
  </tr>
  <tr>
   <td>Prime Mover
   </td>
   <td>The type of generator
   </td>
   <td>EIA
   </td>
   <td>
   </td>
  </tr>
  <tr>
   <td>Subplant
   </td>
   <td>Group of boilers, generators, and stacks that are interconnected at a plant
   </td>
   <td>OGEI
   </td>
   <td>
   </td>
  </tr>
  <tr>
   <td>Plant
   </td>
   <td>
   </td>
   <td>EIA and EPA
   </td>
   <td>
   </td>
  </tr>
</table>
