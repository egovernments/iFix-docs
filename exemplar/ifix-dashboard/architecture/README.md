# Architecture

Fiscal Event services flatten each fiscal event line item and post them into Druid via the Kafka Druid connector. The raw events are stored in the fiscal-events dataset in Druid. [Metabase ](https://www.metabase.com/)is used for visualisations. 

The flattened fiscal event consists of the following attributes

<table>
  <thead>
    <tr>
      <th style="text-align:left">Attribute</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">version</td>
      <td style="text-align:left">
        <p>string
          <br />example: 1.0.0</p>
        <p>Version of the Data Model Definition</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">id</td>
      <td style="text-align:left">
        <p>string
          <br />example: 51c9c03c-1607-4dd5-9e0e-93bbf860f6f7</p>
        <p>System generated UUID of Line Item</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">eventId</td>
      <td style="text-align:left">
        <p>string
          <br />example: fecbbf1d-d6e3-4f24-9935-02c33b9248e0</p>
        <p>Fiscal Event Reference Id</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">tenantId</td>
      <td style="text-align:left">
        <p>string
          <br />nullable: false
          <br />example: pb</p>
        <p>Tenant Id</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">government.id</td>
      <td style="text-align:left">string
        <br />example: pb</td>
    </tr>
    <tr>
      <td style="text-align:left">government.name</td>
      <td style="text-align:left">string
        <br />example: Punjab</td>
    </tr>
    <tr>
      <td style="text-align:left">department.id</td>
      <td style="text-align:left">
        <p>string
          <br />example: 5d664a9f-9367-458a-aa5f-07fb18b90adc</p>
        <p>Unique system generated UUID</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">department.code</td>
      <td style="text-align:left">
        <p>string
          <br />example: DWSS</p>
        <p>Unique department code</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">department.name</td>
      <td style="text-align:left">
        <p>string
          <br />example: Department of Water Supply &amp; Sanitation</p>
        <p>Name of the department</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">expenditure.id</td>
      <td style="text-align:left">
        <p>string
          <br />example: d334d99a-b5c1-426c-942b-f11b5b5454fe</p>
        <p>Unique system generated UUID</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">expenditure.code</td>
      <td style="text-align:left">
        <p>string
          <br />example: JJM</p>
        <p>Unique Expenditure code</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">expenditure.name</td>
      <td style="text-align:left">
        <p>string
          <br />example: Jal Jeevan Mission</p>
        <p>Name of the Expenditure</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">expenditure.type</td>
      <td style="text-align:left">
        <p>string</p>
        <p>Type of the Expenditure Enum:
          <br />Array [ 2 ]</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">project.id</td>
      <td style="text-align:left">
        <p>string
          <br />example: 6ab1b1d2-e224-46fa-b53b-ac83b3c7ce95</p>
        <p>Unique system generated UUID</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">project.code</td>
      <td style="text-align:left">
        <p>string
          <br />example: PWT</p>
        <p>Unique Project code</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">project.name</td>
      <td style="text-align:left">
        <p>string
          <br />example: Peepli Water Tank</p>
        <p>Name of the Project</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">eventType</td>
      <td style="text-align:left">
        <p>string
          <br />nullable: false
          <br />example: Appropriation</p>
        <p>Captures the event type e.g Demand, Receipt, Bill, Payment</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">eventTime</td>
      <td style="text-align:left">
        <p>integer($int64)
          <br />example: 1628177497000</p>
        <p>when the event occurred at source system level</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">referenceId</td>
      <td style="text-align:left">
        <p>string
          <br />example: 013e9c56-8207-4dac-9f4d-f1e20bd824e7</p>
        <p>reference unique id(transaction id) of the caller system</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">parentEventId</td>
      <td style="text-align:left">
        <p>string
          <br />nullable: true
          <br />example: 7d476bb0-bc9f-48e2-8ad4-5a4a36220779</p>
        <p>If this is a follow up event then it will refer to the parent event using
          this reference id.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">parentReferenceId</td>
      <td style="text-align:left">
        <p>string
          <br />nullable: true
          <br />example: 77f23efe-879d-407b-8f23-7b8dd5b2ecb1</p>
        <p>If this is a follow up event then it will refer to the parent event in
          source system using this reference id.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">amount</td>
      <td style="text-align:left">
        <p>number
          <br />example: 10234.5</p>
        <p>Transaction Amount</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">coa.id</td>
      <td style="text-align:left">
        <p>string
          <br />example: e9f940d4-69aa-4bbb-aa82-111b8948a6b6</p>
        <p>Unique system generated UUID</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">coa.coaCode</td>
      <td style="text-align:left">
        <p>string
          <br />example: 1234-123-123-12-12-12</p>
        <p>Chart of account concatenated string</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">coa.majorHead</td>
      <td style="text-align:left">
        <p>string
          <br />example: 1234</p>
        <p>Major head code</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">coa.majorHeadName</td>
      <td style="text-align:left">
        <p>string</p>
        <p>Major head name</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">coa.majorHeadType</td>
      <td style="text-align:left">
        <p>string
          <br />example: Revenue</p>
        <p>Major head code type</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">coa.subMajorHead</td>
      <td style="text-align:left">
        <p>string
          <br />example: 123</p>
        <p>Sub-Major head code</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">coa.subMajorHeadName</td>
      <td style="text-align:left">
        <p>string</p>
        <p>Sub-Major head name</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">coa.minorHead</td>
      <td style="text-align:left">
        <p>string
          <br />example: 123</p>
        <p>Minor head code</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">coa.minorHeadName</td>
      <td style="text-align:left">
        <p>string</p>
        <p>Minor head name</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">coa.subHead</td>
      <td style="text-align:left">
        <p>string
          <br />example: 12</p>
        <p>Sub-Head code</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">coa.subHeadName</td>
      <td style="text-align:left">
        <p>string</p>
        <p>Sub-Head name</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">coa.groupHead</td>
      <td style="text-align:left">
        <p>string
          <br />example: 12</p>
        <p>Group head code</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">coa.groupHeadName</td>
      <td style="text-align:left">
        <p>string</p>
        <p>Group head name</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">coa.objectHead</td>
      <td style="text-align:left">
        <p>string
          <br />example: 12</p>
        <p>Object head code</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">coa.objectHeadName</td>
      <td style="text-align:left">
        <p>string</p>
        <p>Object head name</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">fromBillingPeriod</td>
      <td style="text-align:left">
        <p>integer($int64)
          <br />example: 1622907239000</p>
        <p>Start date of the billing period for which transaction is applicable</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">toBillingPeriod</td>
      <td style="text-align:left">
        <p>integer($int64)
          <br />example: 1628177643000</p>
        <p>Start date of the billing period for which transaction is applicable</p>
      </td>
    </tr>
  </tbody>
</table>

