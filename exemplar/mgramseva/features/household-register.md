# Household Register

**Context**

Users can click on the HouseHold Register on the home screen and navigate to this screen. This provides a single view snapshot of all pending collections by consumers till date.

![](../../../.gitbook/assets/image%20%2848%29.png)

<table>
  <thead>
    <tr>
      <th style="text-align:left"><b>Title</b>
      </th>
      <th style="text-align:left"><b>Explanation</b>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">Heading</td>
      <td style="text-align:left">HouseHold Register</td>
    </tr>
    <tr>
      <td style="text-align:left">As of Date</td>
      <td style="text-align:left">As of &lt;Todays Date&gt;</td>
    </tr>
    <tr>
      <td style="text-align:left">Search</td>
      <td style="text-align:left">
        <ul>
          <li>Search by consumer name or connection id</li>
          <li>Partial match should be allowed.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Filters</td>
      <td style="text-align:left">
        <p>Default is &#x201C;All&#x201D; selected</p>
        <p>User can switch to &#x201C;Pending&#x201D; or &#x201C;Paid&#x201D; view.
          Based on selection, results are displayed in the table</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Download PDF</td>
      <td style="text-align:left">Download PDF should download PDF format of Household Register with name
        of document as HH_Register_&lt;Date&gt;</td>
    </tr>
    <tr>
      <td style="text-align:left">WhatsApp Share</td>
      <td style="text-align:left">Should trigger same PDF as Whatsapp share</td>
    </tr>
    <tr>
      <td style="text-align:left">Columns</td>
      <td style="text-align:left">
        <ul>
          <li>Connection ID
            <ul>
              <li>New Connection ID of the consumer. If there is a metered connection, an
                &#x201C;M&#x201D; in &#x2B55;&#xFE0F; is shown alongside connection ID</li>
            </ul>
          </li>
          <li>Name
            <ul>
              <li>Name of the consumer - Similar to Revenue dashboard truncate it to 20
                characters and show 3 dots</li>
            </ul>
          </li>
          <li>Pending Collections
            <ul>
              <li>Total pending collections of the consumer till date.</li>
            </ul>
          </li>
        </ul>
        <p>The table has sort options by all columns.</p>
        <p>The sorted and filtered table, as in the screen view, is exported into
          the PDF format dynamically on printing.</p>
      </td>
    </tr>
  </tbody>
</table>

Clicking back takes user back to home screen

