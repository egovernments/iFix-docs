# Edit Consumer

## Overview

Consumer information can be edited under certain conditions -

1. Before the first demand is generated from the system
2. After the first demand is generated from the system

![](../../../.gitbook/assets/image%20%2835%29.png)

## Edit Screen

1. Users with permissions to edit consumer records and on clicking the **Edit consumer info** tile on the home screen navigate to the consumer search screen.
2. Users can navigate from the search screen or the search results screen \(Case when multiple search results are displayed\) to the Consumer Edit Screen
3. On successful load of the consumer edit screen, all data parameters of the consumer are shown \(with editable and non-editable fields\)
4. By Default - New consumer ID is shown on the top of the screen and is non-editable 

The table below lists the editable field details -

<table>
  <thead>
    <tr>
      <th style="text-align:left"><b>Data Field</b>
      </th>
      <th style="text-align:left"><b>Before First Demand</b>
      </th>
      <th style="text-align:left"><b>After First Demand</b>
      </th>
      <th style="text-align:left"><b>Comments</b>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">New Consumer ID</td>
      <td style="text-align:left">NO</td>
      <td style="text-align:left">NO</td>
      <td style="text-align:left">Consumer ID is generated while user creation and is not editable</td>
    </tr>
    <tr>
      <td style="text-align:left">Consumer&#x2019;s Name</td>
      <td style="text-align:left">YES</td>
      <td style="text-align:left">YES</td>
      <td style="text-align:left">Bills, receipts, Bill generation screens etc will start displaying the
        newly entered consumer name</td>
    </tr>
    <tr>
      <td style="text-align:left">Gender</td>
      <td style="text-align:left">YES</td>
      <td style="text-align:left">YES</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">Father&#x2019;s Name</td>
      <td style="text-align:left">YES</td>
      <td style="text-align:left">YES</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">Phone number</td>
      <td style="text-align:left">YES</td>
      <td style="text-align:left">YES</td>
      <td style="text-align:left">
        <p>Use Cases</p>
        <ol>
          <li>After the phone number is changed, searching with the old/new phone number
            in the connection search screen leads to the same HH screen.</li>
          <li>SMS notifications are sent to the new mobile number of the user from the
            date of the change.</li>
        </ol>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Old Connection ID</td>
      <td style="text-align:left">YES</td>
      <td style="text-align:left">NO</td>
      <td style="text-align:left">Validated for unique IDs in the system for the GPWSC</td>
    </tr>
    <tr>
      <td style="text-align:left">Door Number</td>
      <td style="text-align:left">YES</td>
      <td style="text-align:left">YES</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">Street Number / Name</td>
      <td style="text-align:left">YES</td>
      <td style="text-align:left">YES</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">Ward Number / Name</td>
      <td style="text-align:left">YES</td>
      <td style="text-align:left">YES</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">Gram Panchayat Name</td>
      <td style="text-align:left">NO</td>
      <td style="text-align:left">NO</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">Property Type</td>
      <td style="text-align:left">YES</td>
      <td style="text-align:left">YES</td>
      <td style="text-align:left">Charges applicable as per rate master. Effects will take place from the
        next billing cycle</td>
    </tr>
    <tr>
      <td style="text-align:left">Service Type</td>
      <td style="text-align:left">YES</td>
      <td style="text-align:left">YES</td>
      <td style="text-align:left">
        <ul>
          <li>Effects will take place from the next billing cycle.</li>
          <li>The last date of the current billing cycle will be taken as the last meter
            reading date.</li>
          <li>Previous meter reading will be captured while generating the demand</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Meter Number</td>
      <td style="text-align:left">YES</td>
      <td style="text-align:left">YES</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">Previous meter reading Date</td>
      <td style="text-align:left">YES</td>
      <td style="text-align:left">NA</td>
      <td style="text-align:left">This field is not shown on screen after the first demand is generated</td>
    </tr>
    <tr>
      <td style="text-align:left">Previous Meter Reading</td>
      <td style="text-align:left">YES</td>
      <td style="text-align:left">NA</td>
      <td style="text-align:left">This field is not shown on the screen after the first demand is generated</td>
    </tr>
    <tr>
      <td style="text-align:left">Last Billing Cycle Billed</td>
      <td style="text-align:left">YES</td>
      <td style="text-align:left">NA</td>
      <td style="text-align:left">This field is not shown on the screen after the first demand is generated</td>
    </tr>
    <tr>
      <td style="text-align:left">Arrears as of Last Bill</td>
      <td style="text-align:left">YES</td>
      <td style="text-align:left">NA</td>
      <td style="text-align:left">This field is not shown on the screen after the first demand is generated.
        When changed the arrear demand is deleted and updated accordingly based
        on the selected service type.</td>
    </tr>
    <tr>
      <td style="text-align:left">Mark Connection as inactive</td>
      <td style="text-align:left">YES</td>
      <td style="text-align:left">YES</td>
      <td style="text-align:left">
        <p>If a connection is marked inactive, it is not considered for demand generation
          for future billing cycles.</p>
        <p>An inactive connection can be reactivated later from this screen.</p>
      </td>
    </tr>
  </tbody>
</table>

## Edit Options

1. Users can create connections without arrears after which the demand is generated.
2. Users can modify the arrear value while updating if it is valid. In such a case, demand is updated with the updated value.
3. Users can add arrear to the connection for which arrear was zero while creating connection. In this case, the new demand is generated.

Clicking on the Submit button shows a nudge saying **Details Submitted Successfully**. Closing the nudge navigates the user back to the Home Screen.

The CTA is activated only when any field is changed or updated. Else, it is in an inactive state.

|  |  |  |
| :--- | :--- | :--- |
|  |  |  |
|  |  |  |

