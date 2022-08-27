---
stoplight-id: partial_cems_plant
---

### Shaping EIA subplants with partial CEMS plant data

In certain cases, there is hourly CEMS data reported for some, but not all subplants at a single plant. In this case, we use the combined hourly profile of the subplants that do report to CEMS to shape the monthly data for the subplants that do not report any data to CEMS. This approach assumes that the hourly operational of all subplants at a single plant will be similar, although further research is needed to establish the accuracy of this assumption.

To calculate the profiles used to shape the data, the pipeline calculates the total net generation and fuel consumption for each plant-hour, and converts each hourly value to a percentage of the monthly total value. This percentage is then multiplied by the monthly total value for the subplants that we are shaping to get the hourly profile. 

Net generation is shaped using the net generation profile, and all fuel and emissions-related totals are shaped using the fuel consumption profile. If one of these profiles is missing, the other is used in its place (for example, if there is no net generation profile, the fuel consumption profile is used to shape the net generation data). Additionally, if the monthly net generation total is negative, it is assigned a flat hourly profile. 