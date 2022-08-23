---
stoplight-id: ba_aggregation
---

## Aggregating plant data to balancing authority

In addition to plant-level data, OGEI includes data aggregated to the balancing authority level.

As explained in the eGRID technical support documentation:


    A balancing authority is a portion of an integrated power grid for which a single dispatcher has operational control of all electric generators. A balancing authority is the responsible entity that integrates resource plans ahead of time, maintains demand and resource balance within a BA area, and supports interconnection frequency in real time. The balancing authority dispatches generators in order to meet an area’s needs and can also control load to maintain the load-generation balance.

Balancing authorities are assigned to each plant based on plant-level data reported in EIA-860. For plants that do not belong to a specific BA, we assign a miscellaneous BA code based on the two-letter state code of the state where the plant is located. For example, many plants in Alaska will be assigned the code “AKMS” and many plants in Hawaii will be assigned a code of “HIMS.” For any plants that are associated with a balancing authority that is no longer active, we also replace the retired BA code with a state-based miscellaneous code. 
