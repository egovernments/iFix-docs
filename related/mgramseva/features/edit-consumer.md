# Edit Consumer

The Consumer information that can be edited under certain conditions

1. Before first demand is generated from system
2. After first demand is generated from system

![](../../../.gitbook/assets/image%20%2835%29.png)

1. User with permissions to edit consumer record and on clicking “ Edit consumer info” tile on home screen will go to consumer search screen.
2. User can come from search screen or search results screen \(Case when multiple search results are displayed\) to Consumer Edit Screen
3. On Successful load of the consumer edit screen, all data parameters of the consumer are shown \(with editable and non editable fields\)
4. By Default - New consumer ID is shown on the top of the screen and is non editable 

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
      <td style="text-align:left">Consumer ID is generated while user creation and wont be editable</td>
    </tr>
    <tr>
      <td style="text-align:left">Consumer&#x2019;s Name</td>
      <td style="text-align:left">YES</td>
      <td style="text-align:left">YES</td>
      <td style="text-align:left">Bills, receipts, Bill generation screens etc where ever consumer name
        is shown, should start showing newly entered name.</td>
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
          <li>After phone number is changed, searching with old/new phone number in
            connection search screen will lead to same HH screen.</li>
          <li>SMS notifications should be sent to new mobile number of user from &amp;
            onwards the date of change.</li>
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
      <td style="text-align:left">Charges applicable as per rate master. Effects will take place from next
        billing cycle</td>
    </tr>
    <tr>
      <td style="text-align:left">Service Type</td>
      <td style="text-align:left">YES</td>
      <td style="text-align:left">YES</td>
      <td style="text-align:left">
        <ul>
          <li>Effects will take place from next billing cycle.</li>
          <li>Last date of current billing cycle will be taken as last meter reading
            date.</li>
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
      <td style="text-align:left">Field wont be shown after first demand is generated</td>
    </tr>
    <tr>
      <td style="text-align:left">Previous Meter Reading</td>
      <td style="text-align:left">YES</td>
      <td style="text-align:left">NA</td>
      <td style="text-align:left">Field wont be shown after first demand is generated</td>
    </tr>
    <tr>
      <td style="text-align:left">Last Billing Cycle Billed</td>
      <td style="text-align:left">YES</td>
      <td style="text-align:left">NA</td>
      <td style="text-align:left">Field wont be shown after first demand is generated</td>
    </tr>
    <tr>
      <td style="text-align:left">Arrears as of Last Bill</td>
      <td style="text-align:left">YES</td>
      <td style="text-align:left">NA</td>
      <td style="text-align:left">Field wont be shown after first demand is generated. When changed the
        arrear demand will get deleted and updated accordingly based on the service
        type changed. Phani Kiran , this will need to be taken care of specifically.</td>
    </tr>
    <tr>
      <td style="text-align:left">Mark Connection as inactive</td>
      <td style="text-align:left">YES</td>
      <td style="text-align:left">YES</td>
      <td style="text-align:left">
        <p>If a connection is marked inactive, it wont be considered for demand generation
          for following billing cycles.</p>
        <p>An inactive connection can later be again made active by coming to this
          screen</p>
      </td>
    </tr>
  </tbody>
</table>



1. User can create connection with out arrears then demand should be generated
2. User can modify the arrear value while update when it is valid, in this case demand should be updated with the updated value
3. User can add arrear to the connection for which arrear was zero while creation connection. in this case new demand should be generated.

Clicking on submit will show nudge saying “ Details submitted successfully” . Closing the nudge will send user back to Home Screen.

Only if any field is changed compared to currently saved fields, the CTA should become active, Else it will be in inactive state.

|  |  |  |
| :--- | :--- | :--- |
|  |  |  |
|  |  |  |

