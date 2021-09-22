# Bulk Demand Generation for Non Metered



Bulk Demand would be generated in 2 methods -

1. Auto \(scheduler based\)
2. Manual
3. **Auto**: The demand is generated at end of the month or the first day of next month or as scheduled for the recently completed Billing cycle. Use cases will be as below
   1. **First demand generated in system**: The demand would be generated for the recently completed billing cycle considering the arrears in the master data. The arrears would be tagged to previous billing cycle of the current demand.
   2. **Consecutive Demands**: The demand would be generated for all the months pending from the most recent to the last billing cycle completed.
   3. The demand would be generated for the recently completed billing cycle.
4. **Manual**: The demand is generated for the Billing cycle that is selected by the user. If the demand is already generated, then the demand would be generated only for those consumers for whom demand does not exist for the selected month.
   1. **First demand generated in system**: The demand would be generated for the selected billing cycle. considering the arrears in the master data. The arrears would be tagged to previous billing cycle of the current demand.
   2. **Consecutive demand**: The demand for the selected month will be generated only if the previous billing cycle demand exist. If the demand for previous cycle does not exist, it would give an error message “Demand generation is pending from billing cycle - &lt;Name of cycle&gt;. please generate demand from this cycle in sequence”. This validation is done considering the most recent billing cycle that exist in the system.

**Charges/Heads and calculation logic:**

As part of V1, only water charges head is only the head that will be applicable. Rate Master would be defined at GPWSC level.

**Water Charges** - Charges will be applicable as defined in the Rate Masters based on - Validity, Property Type, Service Type where calculation type is **“Per Bill Cycle”** for the given billing period.

**Bill Period** - The Billing periods are monthly as standard across GPWSC. In Future, GPWSC may switch to bi-monthly to reduce the processing effort. The Sample billing period data is given in the MDMS data.

**Exclusion:**

* Reversion of Demand is not allowed. This will have to be taken up in the Backend.
* Exception reporting for every batch processing should be accessed from backend only.

