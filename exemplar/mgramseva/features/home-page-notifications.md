# Home Page Notifications

For mGramSeva users, different notifications will be shown on home screen based on different system triggers.

![](../../../.gitbook/assets/image%20%288%29.png)

1. A new card will be used for each notification displayed below.
2. Card will have countdown timer - today, 1 day ago, 2 days ago, 3 days ago, and so on.
3. Card should have a close icon to right top corner. Upon closing, card should go away. Cards by default wont have an expiry date.
4. A “New” text will be shown to user whenever there is a new notification after the user last time login.
5. Beside the heading Notifications show in brackets - how many notifications are there for him.

<table>
  <thead>
    <tr>
      <th style="text-align:left"><b>Trigger</b>
      </th>
      <th style="text-align:left"><b>When</b>
      </th>
      <th style="text-align:left"><b>Text</b>
      </th>
      <th style="text-align:left"><b>Action</b>
      </th>
      <th style="text-align:left"><b>Data criteria</b>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">New Demand Generation</td>
      <td style="text-align:left">Monthly</td>
      <td style="text-align:left">
        <p><b>Demand Generated</b>
        </p>
        <p>Demand for &lt;billing cycle&gt; has been generated. X bills have been
          raised and sent to X/X+Y households. Y bills have to be raised. Click here
          to see details</p>
      </td>
      <td style="text-align:left">Take to filtered view of household register with &#x201C;Pending&#x201D;
        selected</td>
      <td style="text-align:left">&lt;billing cycle&gt; - new billing cycle for which demand is generated.
        <br
        />- Demand will be generated on 1st of each month.</td>
    </tr>
    <tr>
      <td style="text-align:left">Use - Case 1</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">
        <p>If GP has all non-metered connections then, all X/X bills will be generated
          using bulk demand. Notification will change as following</p>
        <p><b>Demand Generated</b>
        </p>
        <p>Demand for &lt;billing cycle&gt; has been generated. X bills have been
          raised and sent to X/X households. Click here to see details</p>
      </td>
      <td style="text-align:left">Take to filtered view of household register with &#x201C;Pending&#x201D;
        selected</td>
      <td style="text-align:left">
        <p>&lt;billing cycle&gt; - new billing cycle for which demand is generated.</p>
        <ul>
          <li>Demand will be generated on 1st of each month.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Use - Case 2</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">
        <p>If GP has all metered connections then, all 0/Y bills will be generated
          using bulk demand. Notification will change as following</p>
        <p><b>New Billing Cycle</b>
        </p>
        <p>New billing cycle will start today. Y bills have to be raised for last
          month. Click here to see details</p>
      </td>
      <td style="text-align:left">Take to filtered view of household register with &#x201C;All&#x201D; selected</td>
      <td
      style="text-align:left">
        <p>&lt;billing cycle&gt; - new billing cycle for which demand is generated.</p>
        <ul>
          <li>Demand will be generated on 1st of each month.</li>
        </ul>
        </td>
    </tr>
    <tr>
      <td style="text-align:left">Every fortnight</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">
        <p><b>Pending Collections</b>
        </p>
        <p>Rs.X is pending collection as of &lt;Today&apos;s Date&gt;. Click here
          to view dashboard</p>
      </td>
      <td style="text-align:left">Take to current months revenue Dashboard</td>
      <td style="text-align:left">In the current financial year, for each consumer, demand raised minus
        receipt generated will be pending collections for that HH</td>
    </tr>
    <tr>
      <td style="text-align:left">When collection happens</td>
      <td style="text-align:left">Collection Day</td>
      <td style="text-align:left">
        <p>Send only on the days when a collection has happened either online or
          offline methods</p>
        <p><b>Todays Collections</b>
        </p>
        <p>Rs. P has been collected today for water charges from &lt;number&gt; consumers
          in Cash.</p>
        <p>Rs. Q has been collected today for water charges from &lt;number&gt; consumers
          online.</p>
      </td>
      <td style="text-align:left">Take to current months revenue Dashboard</td>
      <td style="text-align:left">Sum of receipts value generated that day in that GP via cash.</td>
    </tr>
    <tr>
      <td style="text-align:left">New Calendar Month</td>
      <td style="text-align:left">1st day of month</td>
      <td style="text-align:left">
        <p><b>Month Summary</b>
        </p>
        <p>Rs. X has been collected in &lt;previous month&gt; for water charges and
          Rs. Y has been spent as expenditure. Click here to view more details</p>
      </td>
      <td style="text-align:left">Go to most recent completed month&apos;s dashboard</td>
      <td style="text-align:left">
        <p>X - Sum of receipts value generated that day in that GP via cash.</p>
        <p>Y - Expense Bills marked as paid last month (paid date is previous month)</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Every fortnight</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">
        <p><b>Enter a New Expenditure</b>
        </p>
        <p>Please enter new expenditure bills online. Click here to make an expense
          entry now.</p>
      </td>
      <td style="text-align:left">Take to expense entry screen</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">Alternate fortnight</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">
        <p><b>Mark expense bills as paid</b>
        </p>
        <p>This should only be sent when there is a pending bill is there. If all
          bills are paid already on the date of notification, do not send this.</p>
        <p>&lt;N&gt; expenditure bills are awaiting payment confirmation. Click here
          to search &amp; mark as paid, if paid already.</p>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">Bulk Demand generation doesn&apos;t happen as per schedule</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">
        <p><b>Generate Demand</b>
        </p>
        <p>We couldn&apos;t generate demand automatically for billing cycle &lt;cycle&gt;.
          Click here to generate demand manually.</p>
      </td>
      <td style="text-align:left">Take to demand generation screen.</td>
      <td style="text-align:left"></td>
    </tr>
  </tbody>
</table>

