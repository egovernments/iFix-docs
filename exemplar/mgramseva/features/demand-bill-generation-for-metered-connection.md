# Demand/Bill Generation for Metered Connection

For Metered connection, the demand is generated for the Billing period \(defined based on the meter reading date\) that is selected by the user at the time of recording the meter reading. The 2 uses case that are to be handled -

1. **First demand generated in system**: The demand would be generated for the selected billing period. The demand period would be from “Previous meter reading date” from the consumer master or the demand created as part of master TO the date entered in the billing screen. The arrears would be tagged to previous billing period of the current demand, and the period is from start of FY to the “Previous meter reading date” from the consumer master .
2. **Consecutive demand**: The demand will be generated for the period defined based on
   1. From Date : Meter reading date from last demand generated for the Consumer.
   2. To Date : Is the selected meter reading date in the bill generation screen

**Charges/Heads and calculation logic:**

As part of V1, only water charges head is only the head that will be applicable. Rate Master would be defined at GPWSC level.

**Water Charges** - Charges will be applicable as defined in the Rate Masters based on - Validity, Property Type, Service Type where calculation type is **“Unit Rate”** for the given number of units.

**Bill Period** - Will be as per the date range selected for the Bill generation.

**Exclusion:**

* Reversion of Demand is not allowed. This will have to be taken up in the Backend.

