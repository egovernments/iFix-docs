# Billing - Bulk Demand Generation

All GPs will have a monthly billing cycle for water charges.  Scheduler will automatically trigger on “X” date of every month to generate demand and raise bill for non metered connections.

* Metered connections will not fall under bulk demand generation

1. For the first month of go live, it is only the arrears and no demand will be generated and hence no bill to collect payments
2. From second month \(X date of Month 2\) onwards, demand will be generated.
3. Once the demand is generated a notification will be seen in mGramSeva for all users.
   1. Details of Notification
      1. “Demand for water charges has been raised for &lt;GP&gt;. New Bill Amount is Rs. Xyz. Overall pending amount is Rs.AbcD”
4. Each non metered household will also get notifications
   1. SMS Notification with Bill PDF
      1. Dear “username”, A new water bill has been generated against &lt;connection ID&gt;. Please download the bill using &lt;link&gt;
   2.  SMS notification with Link to payment
      1. Dear “username”, A new water bill has been generated against &lt;connection ID&gt;. Please pay the bill online to avoid late payment charges&lt;link&gt;
5. Revenue collector when on HH Details screen will see a new card \(Updated card from month 2 onwards\) with information related to demand and payment collection.
6. There is also a demand collection Tile/Card on home screen.
   1. This will be used in cases when scheduler is not run\(due to technical errors\) and GP wants to run manually.
7. If the manual demand generation is done in middle of the billing cycle for which demand has already been generated this will do nothing.
   1. Only when scheduler has not generated a demand for a billing cycle, manual demand generation helps.

For Demand Generation Logic refer [Bulk Demand Generation for Non Metered](bulk-demand-generation-for-non-metered.md)

In the Bulk Demand screen, 

**Service Category:** Defaulted to Water Charges\(Module\)

**Service Type:** Defaulted to “Non-Metered”

**Billing Year:** Drop down with list of Financial year from master.

**Billing Cycle:** Drop Down with list of list of Billing cycle for the selected financial year.

On Click of Generate Demand, demand for the given billing cycle will get generated based on the logic defined above.

![](../../../.gitbook/assets/image%20%2812%29.png)



