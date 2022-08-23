---
stoplight-id: validation_checks
---

TODO: Maybe move this to other parts of the documentation

* EIA-923 specific validation tests
    * Check that the allocation fraction for each plant prime mover sums to 1
    * Check that fuel and emissions values are > 0
    * Check that fuel consumption is reported if positive net generation is reported
    * Check that fuel consumed for electricity &lt; total fuel consumption
    * Check for missing calculated emissions values
    * Check for generator-months where all reported data is missing
    * Check for generator-months where all reported data are zero
    * Check that an energy source code has been assigned to all generators
    * Calculate heat rates for each generator, and identify potential outliers by fuel type
* CEMS specific validation tests
    * Check that fuel and emissions values are > 0
    * Check that fuel consumption is reported if positive net generation is reported
    * Check that fuel consumed for electricity &lt; total fuel consumption
    * Check for missing calculated emissions values
    * Check that an energy source code has been assigned to all generators