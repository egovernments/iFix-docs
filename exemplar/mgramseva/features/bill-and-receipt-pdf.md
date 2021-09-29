# Bill and Receipt PDF

![Non Metered Bill](../../../.gitbook/assets/image%20%2837%29.png)

![Metered Bill](../../../.gitbook/assets/image%20%2822%29.png)

Bill and Receipt PDFs can be sent to consumers at multiple touchpoints

1. When bulk demand is generated through SMS
2. When meter reading is done for metered connections, via SMS
3. When revenue collector goes to HH screen and clicks on download PDF \(into his mobile\)
4. When revenue collector goes to HH screen and clicks on WhatsApp share PDF \(Share PDF’s on WhatsApp\)

Bill PDF

<table>
  <thead>
    <tr>
      <th style="text-align:left"><b>Data Parameter</b>
      </th>
      <th style="text-align:left"><b>Explanation</b>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">Title</td>
      <td style="text-align:left">Gram Panchayat Water Supply and Sanitation</td>
    </tr>
    <tr>
      <td style="text-align:left">Heading</td>
      <td style="text-align:left">Water Bill</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <ul>
          <li>Name of GPWSC</li>
          <li>Connection ID</li>
          <li>Consumer Name</li>
          <li>Consumer Mobile Number</li>
          <li>Consumer Address</li>
        </ul>
      </td>
      <td style="text-align:left">
        <p>As per user details (use mockups for reference)</p>
        <ul>
          <li>GPWSC Name should be highlighted</li>
          <li>Phone number should be partially masked</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <ul>
          <li>Service Type</li>
          <li>Bill ID</li>
          <li>Bill Period</li>
          <li>Bill Date</li>
        </ul>
      </td>
      <td style="text-align:left">
        <p><b>Service Type</b> - As per Bill generated - Metered or Non metered.</p>
        <p><b>Bill Id</b> - For metered connections, after service type - metered,
          add meter number, meter reading and meter reading date as additional fields
          before bill ID</p>
        <p><b>Bill Period</b> - For non- metered - As per Billing cycle for which
          demand was generated. For metered, will based on the previous meter reading
          date of last bill and current meter reading date of the corresponding Bill.</p>
        <p><b>Bill Issue Date</b> - Date on which the demand was generated.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Text Above breakup of charges</td>
      <td style="text-align:left">Below is the breakup of pending water charges for the connection ID &lt;New
        Connection ID&gt;</td>
    </tr>
    <tr>
      <td style="text-align:left">Breakup of Charges</td>
      <td style="text-align:left">
        <p>Expansions of the amount to be paid.</p>
        <p>For non metered connections</p>
        <ol>
          <li>Current water charges is the most recent billing cycle completed</li>
          <li>Arrears are the previous billing cycles pending dues arranged in decreasing
            order by months</li>
        </ol>
        <p>For metered connections</p>
        <ol>
          <li>Current charges are the amounts levied for the most recent bill read,
            previous bill read.</li>
          <li>Arrears are the previous dues in similar fashion</li>
        </ol>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Total Amount Due</td>
      <td style="text-align:left">Total Amount to be paid by consumer until time of bill generation (Also
        display in words)</td>
    </tr>
    <tr>
      <td style="text-align:left">Previous Billing Cycle Summary</td>
      <td style="text-align:left">
        <p>Under this section we&#x2019;ll display data collected from user, along
          with collection and expenditure done by GP</p>
        <p>Example: If the bill is generated in November for October and previous
          months(arrears), all data shown will be w.r.t October.</p>
        <p><b>Text:</b> Below is the User Feedback, Collections and Expenditure summary
          of &lt;GPWSC&gt;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">User ratings</td>
      <td style="text-align:left">Irrespective of service type, ratings of how many ever users, given in
        the last billing cycle, is shown.</td>
    </tr>
    <tr>
      <td style="text-align:left">Collections</td>
      <td style="text-align:left">
        <p>New Demand - Latest Demand generated</p>
        <p>Actual Collections - Actual collections made in the previous billing cycle</p>
        <p>Total pending Collections (cumulative) - Total pending collections for
          GP until the last date of the previous billing cycle</p>
        <ul>
          <li>If the same bill is downloaded by a user after n days and more collections
            are made by GP by that date, pending collections number should go down.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Expenditure</td>
      <td style="text-align:left">
        <p>New Expenditure - Expenses logged in the previous billing month</p>
        <p>Actual Payments - actual payments made in the previous billing month</p>
        <p>Total Pending Expenditure (cumulative)- total pending expenses until last
          date of the previous billing month</p>
        <ul>
          <li>If the bill is downloaded again after few expenses are marked paid, the
            cumulative figures will go down.</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

Receipt PDF

![Receipt](../../../.gitbook/assets/image%20%2815%29.png)

<table>
  <thead>
    <tr>
      <th style="text-align:left"><b>Data Parameter</b>
      </th>
      <th style="text-align:left"><b>Explanation</b>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">Title</td>
      <td style="text-align:left">Gram Panchayat Water Supply and Sanitation</td>
    </tr>
    <tr>
      <td style="text-align:left">Heading</td>
      <td style="text-align:left">Water Bill</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <ul>
          <li>Name of GPWSC</li>
          <li>Connection ID</li>
          <li>Consumer Name</li>
          <li>Consumer Mobile Number</li>
          <li>Consumer Address</li>
        </ul>
      </td>
      <td style="text-align:left">
        <p>As per user details (use mockups for reference)</p>
        <ul>
          <li>GPWSC Name should be highlighted</li>
          <li>Phone number should be partially masked</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <ul>
          <li>Service Type</li>
          <li>Receipt ID</li>
          <li>Receipt Period</li>
          <li>Receipt Issue Date</li>
        </ul>
      </td>
      <td style="text-align:left">
        <p>As per the Receipt generated -</p>
        <p>For metered connections, after service type - metered, add meter number
          and meter reading as additional fields before Receipt ID</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Text</td>
      <td style="text-align:left">Below is the breakup of the amount paid for water charges for connection
        ID &lt;New Connection ID&gt;</td>
    </tr>
    <tr>
      <td style="text-align:left">Breakup of Charges</td>
      <td style="text-align:left">
        <p>Expansions of amount to be paid.</p>
        <p>For non metered connections</p>
        <ol>
          <li>Current water charges is the most recent billing cycle completed</li>
          <li>Arrears are the previous billing cycles pending dues arranged in decreasing
            order by months</li>
        </ol>
        <p>For metered connections</p>
        <ol>
          <li>Current charges are the amounts levied for the most recent bill read,
            the previous bill read.</li>
          <li>Arrears are the previous dues in a similar fashion</li>
        </ol>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Amount Paid</td>
      <td style="text-align:left">
        <p>Total Amount paid by the consumer for the receipt to get generated</p>
        <ul>
          <li>Show amount paid in words also</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Due Amount</td>
      <td style="text-align:left">
        <ul>
          <li>As of date, time (day receipt is generated)</li>
          <li>The total amount yet to be paid</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Previous Billing Cycle Summary</td>
      <td style="text-align:left">
        <p>Under this section we&#x2019;ll display data collected from user, along
          with collection and expenditure done by GP</p>
        <p>Example: If the bill is generated in November for October and previous
          months(arrears), all data shown will be w.r.t October.</p>
        <p><b>Text:</b> Below is the User Feedback, Collections and Expenditure summary
          of &lt;GPWSC&gt;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">User ratings</td>
      <td style="text-align:left">Irrespective of service type, ratings of how many ever users, given in
        the last billing cycle, is shown.</td>
    </tr>
    <tr>
      <td style="text-align:left">Collections</td>
      <td style="text-align:left">
        <p>New Demand - Latest Demand generated</p>
        <p>Actual Collections - Actual collections made in the previous billing cycle</p>
        <p>Total pending Collections (cumulative) - Total pending collections for
          GP until the last date of the previous billing cycle</p>
        <ul>
          <li>If the same bill is downloaded by a user after n days and more collections
            are made by GP by that date, pending collections number should go down.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Expenditure</td>
      <td style="text-align:left">
        <p>New Expenditure - Expenses logged in the previous billing month</p>
        <p>Actual Payments - actual payments made in the previous billing month</p>
        <p>Total Pending Expenditure (cumulative)- total pending expenses until last
          date of the previous billing month</p>
        <ul>
          <li>If the bill is downloaded again after few expenses are marked paid, these
            cumulative figures will go down.</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

