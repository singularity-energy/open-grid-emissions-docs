---
stoplight-id: egrid_validation
---

Primary differences with eGRID methodology:



* We use an updated NOx emission factor for flared landfill gas when calculating adjusted emissions from LFG generators.
* We calculate the electric allocation factor for CHP plants for each month, rather than using an annual average electric allocation factor (which is what eGRID uses.

<table>
  <tr>
   <td>
Method/approach
   </td>
   <td>eGRID2020
   </td>
   <td>Open Grid Emissions 
   </td>
   <td>Impact
   </td>
  </tr>
  <tr>
   <td>CAMD data used
   </td>
   <td>Uses annual total CEMS data
   </td>
   <td>Uses hourly CEMS data
   </td>
   <td>Allows OGE to identify missing and anomalous values in CEMS
   </td>
  </tr>
  <tr>
   <td>Allocation of EIA-923 fuel and generation data to generators
   </td>
   <td>Based on generator nameplate capacity
   </td>
   <td>Based on reported fuel and generation data if available, then based on nameplate capacity
   </td>
   <td>
   </td>
  </tr>
  <tr>
   <td>Assigning geothermal geotype (flash, steam, or binary) to geothermal plants
   </td>
   <td>Assigns a single geotype to each plant
   </td>
   <td>Assigns a generator-specific geotype (there are sometimes multiple types at a single plant), and uses updated geotype classifications based on most recent EIA data
   </td>
   <td>Geothermal CO2 emissions about 3% lower than values calculated in eGRID
   </td>
  </tr>
  <tr>
   <td>Fuel cell emissions
   </td>
   <td>Assumes zero co2 emissions for generators with fuel cell prime movers
   </td>
   <td>Applies fuel-specific emission factor for fuel cells that consume fossil fuels
   </td>
   <td>CO2 emissions for plants with a fuel cell prime mover are more than 800% higher than eGRID values.
   </td>
  </tr>
  <tr>
   <td>NOx emission factor for flared landfill gas
   </td>
   <td>0.02 lb NOx per MMbtu
   </td>
   <td>0.078 lb NOx per MMbtu
   </td>
   <td>Adjusted emissions from LFG will be lower than the eGRID values.
   </td>
  </tr>
  <tr>
   <td>CHP electric allocation factor
   </td>
   <td>A single annual average electric allocation factor is calculated
   </td>
   <td>Month-specific electric allocation factors are calculated
   </td>
   <td>Not calculated
   </td>
  </tr>
  <tr>
   <td>Plant primary fuel determination
   </td>
   <td>Based on fuel consumption reported in CAMD data, otherwise on nameplate capacity.
<p>
Uses MSW rather than MSN or MSB.
   </td>
   <td>Same method, but based on fuel consumption reported in EIA-923. Also uses net generation as a tiebreaker when nameplate capacity for two fuels is equal.
   </td>
   <td>Certain plants are assigned a different primary fuel code
   </td>
  </tr>
  <tr>
   <td>OTH fuel types
   </td>
   <td>
   </td>
   <td>Manually assigns an energy source code to generation with OTH fuel type
   </td>
   <td>Improves coverage of emissions data for these plants (there is no emission factor for OTH fuel, so these emissions would otherwise be zero)
   </td>
  </tr>
  <tr>
   <td>Grid Gross Loss
   </td>
   <td>
   </td>
   <td>
   </td>
   <td>
   </td>
  </tr>
</table>