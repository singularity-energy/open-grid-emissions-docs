---
stoplight-id: emission_factors
---

## Consumption-based Emissions

We use a multi-region input-output model to calculate consumption-based emissions for every balancing authority (BA). At each hour, the MIRO model solves a linear system setting generated emissions equal to the sum of consumed emissions and interchanged emissions across all regions. Generated emissions are given by our Open Grid Emissions dataset, and electricity interchange is given by EIA-930 data. From Chalendar (2019), the linear system is: 



## Consumption-based Emissions

We use a multi-region input-output model to calculate consumption-based emissions for every balancing authority (BA). At each hour, the MIRO model solves a linear system setting generated emissions equal to the sum of consumed emissions and interchanged emissions across all regions. Generated emissions are given by our Open Grid Emissions dataset, and electricity interchange is given by EIA-930 data. From Chalendar (2019), the linear system is: 

> TODO: add equation in latex format


Where _i_ is a region, _x<sub>i</sub> _is the consumed emission intensity in region _i_, _p<sub>i</sub>_ is the electricity produced in region _i_, _U<sub>i</sub>_ is the total import into region _i_, _u<sub>ij</sub>_ is the import from region _i_ to region _j_, and _f<sub>i</sub>_ is the total pollutant produced in region _i_. 

In practice, consumed emissions are generally dirtier than generated emissions in regions which generate clean energy but also import energy from their neighbors (for example, the California ISO, CISO). This is reversed in regions which generate dirty or average energy but import clean energy, for example, the New England ISO (ISNE), which imports hydropower from Quebec. 

**Limitations of a MRIO model**

The MRIO model produces regional averages of consumed emissions, but for large BAs such as CISO, it may not capture the actual emissions used by each customer. The MRIO model assumes that all electricity consumed within a BA is a the same, while in reality, transmission constraints, losses, and spatial heterogeneity of fuel sources can make for variation in consumed emission rates even within a BA. However, calculating these more granular consumed rates requires detailed data on the transmission infrastructure and operational constraints of a BA, which is not publicly available. 

**Assumptions about international trading partners **

Some U.S. balancing authorities have electricity interchange with non-US ISOs, including AESO, BCHA, CEN, CFE, HQT, IESO, MHEB, NBSO, and SPC. EIA-930 data contains interchange from these BAs reported by their U.S. trading partners, but none of our datasets include emissions or generation data for these BAs. In some cases, for example, IESO, generation by fuel type is available from the ISO itself; however, processing these individual data souces is beyond the scope of this data release. Instead, we make the same simplified assumptions about generation from these regions as those used in Chalendar (2021). Specifically, we assume that 100% of electricity imported from BCHA, HQT, or MHEB is hydroelectric, and that all other BAs import the same mix as the U.S. average. This likely overestimates imported emissions in some cases, including, for example, IESO, which actually generates more than 90% of its electricity from a mix of nuclear and hydroelectricity. 

**References**


        de Chalendar, J. A., Taggart, J., & Benson, S. M. (2019). Tracking emissions in the US electricity system. _Proceedings of the National Academy of Sciences_, _116_(51), 25497–25502.[ https://doi.org/10.1073/pnas.1912950116](https://doi.org/10.1073/pnas.1912950116)



Where _i_ is a region, _x<sub>i</sub> _is the consumed emission intensity in region _i_, _p<sub>i</sub>_ is the electricity produced in region _i_, _U<sub>i</sub>_ is the total import into region _i_, _u<sub>ij</sub>_ is the import from region _i_ to region _j_, and _f<sub>i</sub>_ is the total pollutant produced in region _i_. 

In practice, consumed emissions are generally dirtier than generated emissions in regions which generate clean energy but also import energy from their neighbors (for example, the California ISO, CISO). This is reversed in regions which generate dirty or average energy but import clean energy, for example, the New England ISO (ISNE), which imports hydropower from Quebec. 

**Limitations of a MRIO model**

The MRIO model produces regional averages of consumed emissions, but for large BAs such as CISO, it may not capture the actual emissions used by each customer. The MRIO model assumes that all electricity consumed within a BA is a the same, while in reality, transmission constraints, losses, and spatial heterogeneity of fuel sources can make for variation in consumed emission rates even within a BA. However, calculating these more granular consumed rates requires detailed data on the transmission infrastructure and operational constraints of a BA, which is not publicly available. 

**Assumptions about international trading partners **

Some U.S. balancing authorities have electricity interchange with non-US ISOs, including AESO, BCHA, CEN, CFE, HQT, IESO, MHEB, NBSO, and SPC. EIA-930 data contains interchange from these BAs reported by their U.S. trading partners, but none of our datasets include emissions or generation data for these BAs. In some cases, for example, IESO, generation by fuel type is available from the ISO itself; however, processing these individual data souces is beyond the scope of this data release. Instead, we make the same simplified assumptions about generation from these regions as those used in Chalendar (2021). Specifically, we assume that 100% of electricity imported from BCHA, HQT, or MHEB is hydroelectric, and that all other BAs import the same mix as the U.S. average. This likely overestimates imported emissions in some cases, including, for example, IESO, which actually generates more than 90% of its electricity from a mix of nuclear and hydroelectricity. 

**References**


        de Chalendar, J. A., Taggart, J., & Benson, S. M. (2019). Tracking emissions in the US electricity system. _Proceedings of the National Academy of Sciences_, _116_(51), 25497–25502.[ https://doi.org/10.1073/pnas.1912950116](https://doi.org/10.1073/pnas.1912950116)