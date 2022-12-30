---
stoplight-id: primary_fuel
---

## Assigning Primary Fuels

Throughout the data pipeline, it is important to be able to assign a fuel category to each plant (e.g. is this a coal plant? a natural gas plant?). However, some plants consume multiple fuels at the same time, or switch fuels throughout the year, so we assign a "primary" fuel value for categorization. We do this not only for each plant, but for each subplant and each generator as well.

The primary fuel of a plant is assigned based on the `energy_source_code` that has the highest annual volume of `fuel_consumed_mmbtu`, as reported in the EIA-923 generation and fuel table. 

If no fuel consumption data is reported or if there are multiple fuels with the same volume of annual fuel consumption, the primary fuel is based on the `energy_source_code_1` associated with the highest combined generator nameplate capacity, as reported by the EIA-860 Generators file. 

If multiple fuels are associated with the same amount of nameplate capacity at a plant, then the primary fuel is determined based on the energy source code that is associated with the highest annual volume of net generation. 

In rare cases where all of the preceding methods of determining plant primary fuel fail, the plant primary fuel is determined based on the `energy_source_code_1` associated with the most number of generators at a plant.