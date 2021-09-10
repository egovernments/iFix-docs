# Tabular Dashboard - Collection

Clicking on Dashboard on Home screen of User will be taken directly to revenue dashboard of the current month. This is a tabular view with list of consumer records.

Following are the data points/actions needed on the screen

<table>
  <thead>
    <tr>
      <th style="text-align:left"></th>
      <th style="text-align:left"></th>
      <th style="text-align:left"></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">1</td>
      <td style="text-align:left">Search Consumer records</td>
      <td style="text-align:left">
        <ul>
          <li>Search by name or connection ID</li>
          <li>Name should be partial match. As the user starts typing a consumer name,
            respective consumers should get filtered in table displayed below</li>
          <li>Connection ID should be partial match. This will be new connection ID.
            As the user starts typing a New connection ID, respective consumers should
            get filtered in table displayed below</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">1.1</td>
      <td style="text-align:left">Filters</td>
      <td style="text-align:left">
        <ul>
          <li>Default is &#x201C;All&#x201D; View. Switching to Residential or commercial
            will filter table accordingly. Along side the filter, how many consumers
            fall into that filter is shown in number</li>
          <li>Table will also have sort options for each column (ascending, descending)</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">1.2</td>
      <td style="text-align:left">Columns</td>
      <td style="text-align:left">
        <ul>
          <li>Connection ID
            <ul>
              <li>New Connection ID of the consumer- this should be clickable, and take
                user to HH details page</li>
              <li>A metered connection should have &#x201C;M&#x201D; in a &#x2B55;&#xFE0F;
                that is followed across as standard for metered connection</li>
            </ul>
          </li>
          <li>Name
            <ul>
              <li>name of the consumer. Show until 20 Characters and truncate by showing
                3 dots if name is longer</li>
            </ul>
          </li>
          <li>Collections - Amount paid by user in that month.</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

![](../../../.gitbook/assets/image-20210802-100536.png)

