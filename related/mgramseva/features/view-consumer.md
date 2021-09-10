# View Consumer

1. User will land onto this screen when he comes from home screen via
   1. Collect payments → Search Screen → Consumer Details Screen
   2. Download bills & receipts → Search screen → consumer details Screen
   3. Dashboard → Collections → Click on Consumer ID
   4. Household register → Click on Consumer ID
2. This screen contains all information related to HH

Static HH card which displays HH details

1. New Connection ID \(also displayed as heading\)
2. Consumer's name
3. Father's name
4. Phone number
5. Old connection ID
6. Address - Door Number, Street number, Ward \(attached\).
7. Property type
8. Service type
   1. for metered connections meter number is also displayed

**For Non Metered Connection**

1.  When Bill is not generated \(Post rollout until first month\)
   1. Only Data Card is shown - No Actions needs to be taken
   2. After first demand is generated
      1. A new consumer bill/Card gets generated with following data points and actions
         1. As of Billing cycle - Most recent completed billing cycle
            1. Amount -
               1. Current Amount - Most recent completed billing cycle fixed charges
               2. Arrears - Arrears from Data entry for first month. From next month onwards the same field will be used to show any unpaid dues.
            2. Total Amount - Sum of current amount and arrears
         2. Action Items
            1. Download, Share Bill
               1. Clicking on download bill will prompt to download bill for respective amount \(Bill details is given in seperate user story\)
               2. Share bill \(whatsapp icon\) will open sharing sharing options of phone OS and user should be able to share bill via whatsapp
               3. Message to go in whatsapp “ Please find Bill for water charges with Connection ID WS-83121-8312 generated on dd/mm/yyyy” along with bill PDF.
               4. Name of the PDF - “Bill ID”
            2. Collect Payment
               1. Collect payment should take revenue collector to payment collection screen
   3. After First payment collection is done
      1. A reciept history block is visible only after first payment will happen through mgramseva.
      2. List of all the receipts will be shown under this section as cards, with different data points as actions. Order of receipts will be newest → oldest from top to bottom
      3. Each receipt card will contain
         1. Receipt ID
         2. Amount Paid
         3. Paid Date
      4. Actions
         1. Download Receipt - should download receipt in Revenue collectors phone as a PDF
            1. Name of PDF - “Receipt ID”
         2. Share\(WhatsApp\)
            1. Message to go in whatsapp “ Please find receipt for water charges with Connection ID WS-83121-8312 paid on dd/mm/yyyy” along with receipt PDF.

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <ul>
          <li></li>
        </ul>
      </th>
      <th style="text-align:left">
        <ul>
          <li>First bill is generated</li>
          <li>payment collection is pending</li>
        </ul>
      </th>
      <th style="text-align:left">
        <ul>
          <li>2 payments are already made</li>
        </ul>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
  </tbody>
</table>

![New Connection Before First Bill Generation](../../../.gitbook/assets/image%20%2846%29.png)

![First bill is generated   Payment Collection is pending](../../../.gitbook/assets/image%20%2840%29.png)

![2 payments are already made](../../../.gitbook/assets/image%20%2837%29.png)

**For Metered Connection**

1.  When Bill is not generated \(Post rollout until first month\)
   1. Data Card is shown
   2. Below the data card, Card to generate a new bill is also shown.
   3. This card contains
      1. Last bill generation date - For first time this will be picked up from data entry. Next time onwards systems latest bill generation date will be captured.
      2. Days from last bill generation Date - this is to indicate revenue collector how many days has passed by, since last time bill is generated
      3. Previous Meter reading - Units of the meter that is last read will be displayed here.
      4. Pending Amount
         1. Before first bill is generated this will just be arrears that is captured during data entry
         2. After first bill is generated, this pending amount includes whole pending amount by the user
      5. Generate a new bill
         1. Clicking on generate a new bill will initiate bill generation flow for metered connection
      6. Note
         1. User has to generate a bill to start collecting payments, Without first generation of bill, collection cant happen even for arrears entered in data entry.
   4. After first bill is generated
      1. A new consumer bill/Card gets generated with following data points and actions
         1. Last bill generation date - Date of bill generation
            1. Amount -
               1. Current Amount - Volumetric charges between 2 latest meter readings according to rate master
               2. Arrears - All previously unpaid dues.
            2. Total Amount - Sum of current amount and arrears
         2. Action Items
            1. Download, Share Bill
               1. Clicking on download bill will prompt to download bill for respective amount \(Bill details is given in seperate user story\)
               2. Share bill \(whatsapp icon\) will open sharing sharing options of phone OS and user should be able to share bill via whatsapp
               3. Message to go in whatsapp “ Please find Bill for water charges with Connection ID WS-83121-8312 generated on dd/mm/yyyy” along with bill PDF.
               4. Name of the PDF - “Bill ID”
            2. Collect Payment
               1. Collect payment should take revenue collector to payment collection screen
   5. After First payment collection is done
      1. A reciept history block is visible only after first payment will happen through mgramseva.
      2. List of all the receipts will be shown under this section as cards, with different data points as actions. Order of receipts will be newest → oldest from top to bottom
      3. Each receipt card will contain
         1. Receipt ID
         2. Amount Paid
         3. Paid Date
      4. Actions
         1. Download Receipt - should download receipt in Revenue collectors phone as a PDF
            1. Name of PDF - “Receipt ID”
         2. Share\(WhatsApp\)
            1. Message to go in whatsapp “ Please find receipt for water charges with Connection ID WS-83121-8312 paid on dd/mm/yyyy” along with receipt PDF.
   6. If a new bill is generated again by clicking on ‘Generate a new bill’ reveneue collector will go through bill generation flow and a new single card appears between ‘Generate bill’ and ‘Consumer receipts block’

![](../../../.gitbook/assets/image%20%285%29.png)

![](../../../.gitbook/assets/image%20%2833%29.png)

![](../../../.gitbook/assets/image%20%2822%29.png)

