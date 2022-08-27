---
stoplight-id: using_the_data
---

# Summary of the Data

## Files

The data is organized into three categories based on the primary use case

* **Carbon accounting data**: BA-level, _consumption-_based emission rates and fuel mix data. 
    * Intended user: This data is intended for those wishing to understand the source and emission intensity of the electricity they are consuming. 
    * File structure: data for each BA will be located in its own separate file.
* **Power sector data**: BA-level, _production_-based data on generation, emissions, and fuel consumption split out by fuel type. 
    * Intended user: This data is intended for analysts who seek to understand the operating characteristics of the power generation fleets in each region. 
    * File structure: data for each BA will be located in its own separate file
* **Power plant data**: Plant-level data on hourly power plant operations and static attributes of each plant. 
    * Intended user: This data is intended for researchers who seek to understand individual power plants, or who want to perform their own aggregations of the data. 
    * File structure: include all dynamic data in a single large csv (perhaps a tar.gz file) and all static attributes (e.g. fuel type, BA, etc) in a separate table, with the plant_id_eia as the primary key

Each of these data categories includes data at different temporal resolutions (hourly, monthly, annual), and in different units (U.S. and Metric). U.S.-unit files uses lb for mass and MMBtu for fuel consumption, while the metric files use kg for mass and GJ for fuel consumption. 


## Uses and Users

![Example Data Use Cases](Use%20Case%20Table.PNG)

## Data Dictionary

Generally all column names in the OGE dataset are self-descriptive including the units associated with the data, if relevant. Thus, we do not include a full data dictionary for all files here. 

A few notes on column names:
- Data column names generally follow the format `{value_name}_{adjustment_type}_{unit_of_measure}`
- Column names that include the `_for_electricity` adjustment type have been adjusted for CHP (see [methodology](../Methodology/Emissions%20Calculations/Adjusting%20Emissions%20for%20CHP.md)) and represent the portion of the total value that is related to electricity generation.
- Column names that include the `_adjusted` adjustment type have been adjusted for biomass (see [methodology](../Methodology/Emissions%20Calculations/Adjusting%20Emissions%20for%20Biomass.md)).
- Column names that include the `_for_electricity_adjusted` adjustment type have been adjusted for both CHP and biomass.
- The `report_date` column is in the format `MM/01/YYYY` and represents the month `MM` with which the data is associated. So data with a report date of "03/01/2020" is associated with March 2020.

### Plant Static Attributes Table


Field Name | Type | Description
---------|----------|---------
 A1 | B1 | C1
 A2 | B2 | C2
 A3 | B3 | C3