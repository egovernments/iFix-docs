# Revenue Collection - Offline

![](../../../.gitbook/assets/image%20%2839%29.png)

After the demand is generated for Metered and non-metered connections Revenue collector will come to this screen to collect payments.

1. User will see screen Consumer billing information will be seen
2. Clicking on view details will expand the card and show more details. Clicking on Hide details should collapse the card to show only connection ID, Consumer Name & total due amount.
3. Payment amount - Can be made as
   1. Full amounts
   2. Custom Amount - User can enter custom amount in the entry field, which is not zero & not greater than total due amount.
4. Payment methods
   1. Cash - selecting cash and proceeding to payment will take user to successful collection screen
   2. Online - Clicking on online will show a Q/R code on users screen which can be scanned by another phone to pay amount.
   3. Post payment via any mode - payment success screen is shown
   4. Receipt ID format - RB-dd/mm/yyyy-yy/running\_sequence\_number
5. user actions
   1. Download receipt - download PDF version of receipt with receipt ID as name of PDF while downloading
   2. Share receipt via whatsapp - Should open Phone OS sharing options
   3. back to home - should take user back to home screen
6. SMS to HH
   1. As soon as the amount is paid and Revenue collector reaches the Payment success screen SMS will be sent to HH.
      1. SMS 1 - Dear ‘Username’, Paid Rs.X for water charges for bill period &lt;Cycle&gt;. Download receipt &lt;link&gt;
      2. SMS 2 - Dear ‘Username’, Please leave a review on water supply at &lt;GP&gt; at &lt;Link&gt;
      3. HH should be able to leave a review for water charges. Refer [Feedback - Post Payments](feedback-post-payment.md).  

Details on the card

<table>
  <thead>
    <tr>
      <th style="text-align:left"><b>Detail</b>
      </th>
      <th style="text-align:left"><b>Comments</b>
      </th>
      <th style="text-align:left"></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">Connection ID</td>
      <td style="text-align:left">New Connection ID will be displayed here</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">Consumer Name</td>
      <td style="text-align:left">Consumer Name (Should take updated consumer name)</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">Bill ID number</td>
      <td style="text-align:left">ID of the Bill</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">Bill period</td>
      <td style="text-align:left">
        <p>for non-metered connections</p>
        <ol>
          <li>This will be latest billing cycle for which demand is generated</li>
        </ol>
        <p>For metered connections</p>
        <ol>
          <li>This will be new bill generated from meter reading between most recent
            2 billing dates.</li>
        </ol>
      </td>
      <td style="text-align:left">
        <p>Format</p>
        <ol>
          <li>Month &lt;space&gt; Financial Year</li>
          <li>Previous meter reading date - New meter reading date</li>
        </ol>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Water charges</td>
      <td style="text-align:left">Amount for Most recent billing cycle</td>
      <td style="text-align:left">For metered, calculate charges as per rate master between most recent
        2 billing dates</td>
    </tr>
    <tr>
      <td style="text-align:left">Arreas</td>
      <td style="text-align:left">All old arrears accumulated for HH</td>
      <td style="text-align:left">Expansion should breakup of arrears by individual billing cycles/bill
        generation dates</td>
    </tr>
    <tr>
      <td style="text-align:left">Total Due amount</td>
      <td style="text-align:left">Net amount consumer has to pay</td>
      <td style="text-align:left"></td>
    </tr>
  </tbody>
</table>

![](../../../.gitbook/assets/image%20%2850%29.png)

![](../../../.gitbook/assets/image%20%2820%29.png)

1. When Online is selected for payment method, the “Collect Payment” Option is disabled. Since HH will scan the QR and Revenue collector does’t have control on the online process.
2. Partial amount can’t be greater than full amount.

