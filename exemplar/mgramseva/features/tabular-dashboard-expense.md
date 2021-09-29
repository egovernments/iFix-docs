# Tabular Dashboard - Expense

Clicking on the Dashboard on the home screen takes the user directly to the revenue dashboard of the current month. From here, the user can switch to the expenditure tab to get a view of expenses. This provides a tabular view of all expenses incurred in that month.

![](../../../.gitbook/assets/image%20%2813%29.png)

Following are the data points/actions needed on the screen

<table>
  <thead>
    <tr>
      <th style="text-align:left"><a href="http://S.No"><b>S.No</b></a>
      </th>
      <th style="text-align:left"><b>Item</b>
      </th>
      <th style="text-align:left"><b>Explanation</b>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">1</td>
      <td style="text-align:left">Search Expense Bills</td>
      <td style="text-align:left">
        <ul>
          <li>Search by Bill ID or Vendor</li>
          <li>The Vendor Name should be a partial match. As the user starts typing a
            consumer name, respective vendors get filtered in the table displayed below</li>
          <li>Bill ID should be a partial match. As the user starts typing a New Bill
            ID, respective Bills should get filtered in the table displayed below</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">1.1</td>
      <td style="text-align:left">Filters</td>
      <td style="text-align:left">
        <ul>
          <li>Default is &#x201C;All&#x201D; View. Switching to Paid or Pending filters
            the table accordingly. Alongside the filter, how many Bills fall into that
            filter is shown in numbers</li>
          <li>The table also has sort options for each column (ascending, descending)</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">1.2</td>
      <td style="text-align:left">Columns</td>
      <td style="text-align:left">
        <ul>
          <li>Bill ID - Vendor Name
            <ul>
              <li>Bill ID is assigned to each bill while creating an expense entry record</li>
              <li>Sort happens on the Bill ID</li>
            </ul>
          </li>
          <li>Expense Type
            <ul>
              <li>Under which expense head the bill is tagged to</li>
            </ul>
          </li>
          <li>Amount</li>
          <li>Bill Date</li>
          <li>Paid Date
            <ul>
              <li>If Bill is not paid, this should show pending in RED</li>
            </ul>
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

The table on the screen is a horizontal scrollable one with the left-most column fixed.

