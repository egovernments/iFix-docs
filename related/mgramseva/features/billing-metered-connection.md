# Billing - Metered Connection



1. Meter reading entry and acknowledgement screens
2. Download bill PDF on acknowledge screen
3. SMS to HH upon bill generation

**Context**

Unlike Non Metered connections which has a billing cycle for demand & bill to be generated automatically, a metered connection needs more inputs, which helps in volumetric billing

**User story**

1. A revenue collector on HH details screen, can see a CTA to “Generate a new Bill” all the time.
2. Clicking on “Generate a new Bill” will take user to bill generation screen where new meter reading details have to be entered
3. Field on bill generation screen for metered connections are displayed in table below
4. Clicking on “Generate bill” will take user to successful bill generation screen
5. Logic for Bill ID number - “RB - dd/mm/yyyy-yy/running\_sequence\_number”
6. On the success screen there are 3 user actions
   1. Download bill - Download Bill as PDF \(name of PDF will always be Bill ID\)
   2. Share Bill on WhatsApp - Share Bill as PDF on WhatsaApp
   3. Collect Payment - Should take revenue collector to payment collection screen.
7. Share on WhatsApp should open WhatsApp Share directly with an option to choose contacts/groups with text and attached PDF
   1. Text “ Dear &lt;ConsumerName&gt;, Please find water bill for billing cycle &lt;Cycle&gt; attached as PDF”

| **Input Metric** | **UseCase** | **Comments** |
| :--- | :--- | :--- |
| Previous Meter reading | Only for first time bill generation |  |
| New meter reading | For first time and all consecutive bill generations | Previous meter reading units and previous meter reading dates will be taken from last bill for new bill generation |
| Meter reading date | Default will be todays date. Revenue collector can change it to a previous date if required. |  |

For Demand Generation Logic refer to [Demand/Bill Generation for metered connection](demand-bill-generation-for-metered-connection.md).

![Bill Generation screen for Metered connections](../../../.gitbook/assets/image%20%2810%29.png)



![ Bill Generation Successful](../../../.gitbook/assets/image%20%2825%29.png)

1. All 5 Digits in Meter reading has to be entered. Show error message “ Old Meter Reading entered is Invalid” , “ New Meter Reading entered is invalid” respectively.
2. New Meter reading should be greater than old meter reading
3. Meter reading date, default it to &lt;todays date&gt; but give option to change to the user.

