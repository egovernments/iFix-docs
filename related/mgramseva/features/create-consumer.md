# Create Consumer

## Overview

The household masters need to be created in the system to initiate the demand generation and collection process. These are consumers also referred to as the household that will be issued the water connection and supplied on regular basis.

![Non Metered Connection](../../../.gitbook/assets/image%20%2819%29.png)

On selecting the option Create consumer from the list of tile/cards on the home page, the user is navigated to the Create Consumer page. 

Data elements for the consumer listed in the table below -

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
      <td style="text-align:left">Name of the household or connection owner.</td>
    </tr>
    <tr>
      <td style="text-align:left">Gender</td>
      <td style="text-align:left">Radio</td>
      <td style="text-align:left">Y</td>
      <td style="text-align:left">Male, Female, Transgender</td>
    </tr>
    <tr>
      <td style="text-align:left">Father&apos;s Name</td>
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
          <li>For a tenant which has a single ward, the ward field is not shown</li>
          <li>For a tenant which has multiple wards, the ward field is shown as a single
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
      <td style="text-align:left">Dropdown with the list of property types from Master ( Ex - Residential,
        Commercial, Mixed, etc)</td>
    </tr>
    <tr>
      <td style="text-align:left">Service Type</td>
      <td style="text-align:left">Drop Down</td>
      <td style="text-align:left">Y</td>
      <td style="text-align:left">Dropdown with the list of service types from Master (Ex - Metered, Non-metered)</td>
    </tr>
    <tr>
      <td style="text-align:left">Meter Number</td>
      <td style="text-align:left">Alpha - Numeric</td>
      <td style="text-align:left">Y</td>
      <td style="text-align:left"><b>Only for Metered connections -</b> Meter number will be attached to
        consumer respectively</td>
    </tr>
    <tr>
      <td style="text-align:left">Previous meter reading date</td>
      <td style="text-align:left">Date selection</td>
      <td style="text-align:left">Y</td>
      <td style="text-align:left"><b>Only for Metered connections -</b> This field is used to tag arrears
        to a demand. Less than current Date.</td>
    </tr>
    <tr>
      <td style="text-align:left">Previous meter reading</td>
      <td style="text-align:left">Numeric</td>
      <td style="text-align:left">Y</td>
      <td style="text-align:left"><b>Only for Metered connections -</b> This field is used to attach arrears
        to a demand.</td>
    </tr>
    <tr>
      <td style="text-align:left">Last Billing Cycle Billed</td>
      <td style="text-align:left">Drop Down</td>
      <td style="text-align:left">Y</td>
      <td style="text-align:left"><b>Only for Non-metered connections -</b> Dropdown with the list of Billing
        Cycles prior to the current cycle. This field is used to specify the arrears
        or total outstanding as of the billing cycle.</td>
    </tr>
    <tr>
      <td style="text-align:left">Arrears as of Last Bill</td>
      <td style="text-align:left">Numeric</td>
      <td style="text-align:left">Y</td>
      <td style="text-align:left">
        <p>Arrears as of date - This will be considered for the first Demand/Bill
          generation as total outstanding or arrears as of the billing period mentioned.</p>
        <p>If no arrears are present to a HH, &apos;0&apos; has to be entered by
          the user.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Submit</td>
      <td style="text-align:left">Button</td>
      <td style="text-align:left">-</td>
      <td style="text-align:left">On click of Submit button, the consumer master is created with the detail
        entered above. The new connection id is also generated as per the configuration.</td>
    </tr>
  </tbody>
</table>

{% hint style="info" %}
* Multiple connections \(HH records\) can be created with the same phone number.
  * Phone numbers can be the same, but the old connection ID should be different to create a new HH record.
* A single HH record, can't be registered in the system more than once. Trying to register on the system again displays the error message “this connection already exists”.
{% endhint %}

## Additional Notes and Validation

* On Submit, the consumer master is created and the new consumer id is assigned to the master. The consumer id generated is based on logic defined as - “WS-&lt;GP id&gt;-&lt;4 digit running seq No&gt;”
* If the connection id already exists,  an error message is shown accordingly.
* On first time/new load, all data entry fields and dropdowns are empty \(since there are no records prefilled except for the default fields\).
* SMS is not sent to any user upon consumer \(HH\) creation.
* Submit is disabled until all mandatory fields are entered. Once all inputs are made, the button is enabled.
* Arrears demand :
  * Metered - The arrear demand for the period is created, where the From date is counted as the start of the Financial year and the To date as the period mentioned in the screen.
  * Non metered - The arrear demand is created for the selected billing cycle.

## **Successful Actions**

1. On the successful creation of consumer records, a toast message “ Registration successful” is shown.
2. Closing this toast message, using the close icon, refreshes the page and the user sees an empty consumer creation screen.

| **Consumer creation - non metered** | **Consumer creation - metered** |
| :--- | :--- |
|  |  |

