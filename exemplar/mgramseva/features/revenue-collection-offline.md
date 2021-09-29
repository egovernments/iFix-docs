# Revenue Collection - Offline

![](../../../.gitbook/assets/image%20%2839%29.png)

After the demand is generated for Metered and non-metered connections Revenue collectors come to this screen to collect payments.

1. Users can see the consumer billing information on the screen
2. Clicking on View Details expands the card and shows more details. Clicking on the Hide Details collapses the card to show only connection ID, Consumer Name & Total Due Amount.
3. Payment amount - can either pay
   1. The full amount, or
   2. Custom amount - Users can enter the custom amount in the input field - this cannot be zero or greater than the total due amount.
4. Payment methods
   1. Cash - select cash and proceed to payment takes the user to the successful collection screen
   2. Online - The online payment option displays a Q/R code on the user screen that can be scanned by another phone to pay the due.
   3. Post payment via any mode - payment success screen is shown
   4. Receipt ID format - RB-dd/mm/yyyy-yy/running\_sequence\_number
5. User Actions
   1. Download receipt - download PDF version of receipt with receipt ID as the name of PDF while downloading
   2. Share receipt via WhatsApp - opens the Phone OS sharing options
   3. back to home - takes the user back to the home screen
6. SMS to HH
   1. As soon as the amount is paid and the Revenue collector reaches the Payment success screen SMS is sent to HH.
      1. SMS 1 - Dear ‘Username’, Paid Rs.X for water charges for bill period &lt;Cycle&gt;. Download receipt &lt;link&gt;
      2. SMS 2 - Dear ‘Username’, Please leave a review on water supply at &lt;GP&gt; at &lt;Link&gt;
      3. HH is able to leave a review for water charges. Refer [Feedback - Post Payments](feedback-post-payment.md).  

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
          <li>This is the latest billing cycle for which demand is generated</li>
        </ol>
        <p>For metered connections</p>
        <ol>
          <li>This is the new bill generated from the meter reading between the 2 most
            recent billing dates</li>
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
      <td style="text-align:left">Amount for the latest billing cycle</td>
      <td style="text-align:left">For metered, calculate charges as per rate master between the latest 2
        billing dates</td>
    </tr>
    <tr>
      <td style="text-align:left">Arrears</td>
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

1. When online is selected for payment method, the “Collect Payment” option is disabled. Since HH scans the QR, the Revenue collector does not have control over the online process.
2. A partial amount can’t be greater than the full amount.

