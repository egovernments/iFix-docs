# Create Consumer

The house hold masters need to be created in the system to initiate the demand generation and collection. These are consumer or also called as house hold which will be issued the water connection and supplied on regular basis.

![Non Metered Connection](../../../.gitbook/assets/image%20%2818%29.png)

On selecting the option “Create consumer” from the list of tile/cards on the home page, the user will be navigated to this create consumer page. Data elements for the consumer -

<table>
  <thead>
    <tr>
      <th style="text-align:left"><b>Field Name</b>
      </th>
      <th style="text-align:left"><b>Type</b>
      </th>
      <th style="text-align:left"><b>Mandatory Y/N</b>
      </th>
      <th style="text-align:left"><b>Description</b>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">Consumer&#x2019;s Name</td>
      <td style="text-align:left">Text</td>
      <td style="text-align:left">Y</td>
      <td style="text-align:left">Name of the house hold or connection owner.</td>
    </tr>
    <tr>
      <td style="text-align:left">Gender</td>
      <td style="text-align:left">Radio</td>
      <td style="text-align:left">Y</td>
      <td style="text-align:left">Male, Female, Transgender</td>
    </tr>
    <tr>
      <td style="text-align:left">Father;s Name</td>
      <td style="text-align:left">Text</td>
      <td style="text-align:left">Y</td>
      <td style="text-align:left">Name of the father of the owner</td>
    </tr>
    <tr>
      <td style="text-align:left">Mobile Number</td>
      <td style="text-align:left">Numeric</td>
      <td style="text-align:left">Y</td>
      <td style="text-align:left">Mobile number for the consumer</td>
    </tr>
    <tr>
      <td style="text-align:left">Old Connection id</td>
      <td style="text-align:left">Alpha Numeric</td>
      <td style="text-align:left">Y</td>
      <td style="text-align:left">Old connection id or ref number for reference</td>
    </tr>
    <tr>
      <td style="text-align:left">Door Number</td>
      <td style="text-align:left">Alpha Numeric</td>
      <td style="text-align:left">N</td>
      <td style="text-align:left">Address details with door number for the connection</td>
    </tr>
    <tr>
      <td style="text-align:left">Street No/Street Name</td>
      <td style="text-align:left">Alpha Numeric</td>
      <td style="text-align:left">N</td>
      <td style="text-align:left">Street number or name of the house for the connection</td>
    </tr>
    <tr>
      <td style="text-align:left">Ward</td>
      <td style="text-align:left">Drop Down</td>
      <td style="text-align:left">Y</td>
      <td style="text-align:left">
        <ul>
          <li>For a tenant which has a single ward, ward field wont be shown.</li>
          <li>For a tenant which has multiple wards, ward field will be shown as a single
            select dropdown</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Gram Panchayat</td>
      <td style="text-align:left">Display</td>
      <td style="text-align:left">-</td>
      <td style="text-align:left">For info. the GP or tenant in which the connection master is created.</td>
    </tr>
    <tr>
      <td style="text-align:left">Property Type</td>
      <td style="text-align:left">Drop Down</td>
      <td style="text-align:left">Y</td>
      <td style="text-align:left">Drop down with the list of property type from Master ( Ex - Residential,
        Commercial, Mixed, etc)</td>
    </tr>
    <tr>
      <td style="text-align:left">Service Type</td>
      <td style="text-align:left">Drop Down</td>
      <td style="text-align:left">Y</td>
      <td style="text-align:left">Drop down with list of service type from Master (Ex - Metered, Non-metered)</td>
    </tr>
    <tr>
      <td style="text-align:left">Meter Number</td>
      <td style="text-align:left">Alpha - Numeric</td>
      <td style="text-align:left">Y</td>
      <td style="text-align:left"><b>Only for Metered connections</b>. Meter number will be attached to
        consumer respectively</td>
    </tr>
    <tr>
      <td style="text-align:left">Previous meter reading date</td>
      <td style="text-align:left">Date selection</td>
      <td style="text-align:left">Y</td>
      <td style="text-align:left"><b>Only for Metered connections</b>. This field is used to tag arrears
        to a demand. Less than current Date.</td>
    </tr>
    <tr>
      <td style="text-align:left">Previous meter reading</td>
      <td style="text-align:left">Numeric</td>
      <td style="text-align:left">Y</td>
      <td style="text-align:left"><b>Only for Metered connections</b>. This field is used to attach arrears
        to a demand.</td>
    </tr>
    <tr>
      <td style="text-align:left">Last Billing Cycle Billed</td>
      <td style="text-align:left">Drop Down</td>
      <td style="text-align:left">Y</td>
      <td style="text-align:left"><b>Only for Non-metered connections</b>. Drop down with list of Billing
        Cycle prior to current cycle. This field is used to specify the arrears
        or total outstanding as of the billing cycle.</td>
    </tr>
    <tr>
      <td style="text-align:left">Arrears as of Last Bill</td>
      <td style="text-align:left">Numeric</td>
      <td style="text-align:left">Y</td>
      <td style="text-align:left">
        <p>Arrears as of date. This will be considered for the first Demand/Bill
          generation as total outstanding or arrears as of the billing period mentioned.</p>
        <p>If no arrears are present to a HH, &apos;0&apos; has to be entered by
          the user.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Submit</td>
      <td style="text-align:left">Button</td>
      <td style="text-align:left">-</td>
      <td style="text-align:left">On click, the consumer master get created with the detail entered above.
        The new connection id also should get generated as per the configuration.</td>
    </tr>
  </tbody>
</table>

1. Multiple connections\(HH records\) can be created with same phone number.
   1. Phone number can be same, but old connection ID should be different to create a new HH record.
2. A single HH record, can't be registered in the system more than once. The error message “this connection already exists” will be displayed, when trying to submit.

### Additional notes and Validation:

* On Submit, the consumer master should get created and the new consumer id should be assigned to the master. The consumer id generated would be based on logic defined as - “WS-&lt;GP id&gt;-&lt;4 digit running seq No&gt;”
* If the connection id already exist,  error message will be shown accordingly.
* On first time/new load, all data entry fields and drop downs will be empty \(nothing to be prefilled except for defaulted fields\).
* SMS’s will not be sent to any user upon consumer \(HH\) creation.
* Submit will be disabled until all mandatory fields are entered. Once entered this will become enabled.
* Arrears demand :
  * Metered - The arrear demand for the period would be created, where the From date would the start of the Financial year and To date would as mentioned in the screen.
  * Non metered - The arrear demand would be created for the selected billing cycle.

**Successful Actions**

1. On Successful creation of consumer record, a toast message is shown “ Registration successful”
2. Closing this toast message, using the close icon, will refresh the page and user will see empty consumer creation screen.

\*\*\*\*

| **Consumer creation - non metered** | **Consumer creation - metered** |
| :--- | :--- |
|  |  |

