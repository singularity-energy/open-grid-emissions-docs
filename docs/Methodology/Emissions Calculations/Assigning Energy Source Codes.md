---
stoplight-id: assign_esc
---


Historically, any generators that burned municipal solid waste (MSW) reported this fuel consumption under a single fuel code. In recent years, however, EIA-923 began reporting these data under two separate codes for the biogenic portion (MSB) and non-biogenic portion (MSN). This is important because each portion has different emission rates. When calculating emissions from fuel consumption for EIA-923 data, these two separate fuel codes are used. However, when imputing missing emissions data in CEMS, the fuel type assigned to each unit is sourced from the Power Sector Data Crosswalk, which still only uses the MSW fuel code. This will be fixed in future versions of the database, and progress on this issue can be tracked [here](https://github.com/singularity-energy/open-grid-emissions/issues/51).
