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