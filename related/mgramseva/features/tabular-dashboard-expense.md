# Tabular Dashboard - Expense

Clicking on Dashboard on Home screen of User will be taken directly to revenue dashboard of the current month. From here, user can switch to expenditure tab and have an expense view. This provides a tabular view of all expenses done in that month.

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
          <li>Vendor Name should be partial match. As the user starts typing a consumer
            name, respective vendors should get filtered in table displayed below</li>
          <li>Bill ID should be partial match. As the user starts typing a New Bill
            ID, respective Bills should get filtered in table displayed below</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">1.1</td>
      <td style="text-align:left">Filters</td>
      <td style="text-align:left">
        <ul>
          <li>Default is &#x201C;All&#x201D; View. Switching to Paid or Pending will
            filter table accordingly. Along side the filter, how many Bills fall into
            that filter is shown in number</li>
          <li>Table will also have sort options for each column (ascending, descending)</li>
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
              <li>Sort should happen based on Bill ID</li>
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

Table on the screen is horizontal scrollable one with left most column fixed.

