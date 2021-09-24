# Generate Bill

## Manual Bulk Demand Generation

**Link**

→ {base url}/mgramseva/home/billmanualgenerate.

![](../../../../.gitbook/assets/image%20%2862%29.png)

Users are redirected to this screen if they click on the Generate Demand card on the home screen.

* This will be used in cases when the scheduler is not run \(due to technical errors\) and GP wants to run manually.

### **Default Values Set**

* The service category displays water charges by default
* The service type displays non-metered connection by default

### **User Interaction on Screen**

* Set the billing year from the drop-down which contains the list of financial years.
* Set the Billing cycle which contains billing cycles for the selected financial year.
* On Click of Generate Demand Button, Bulk Demand is generated and the user is navigated to the success screen.

![](../../../../.gitbook/assets/image%20%2859%29.png)

### **Logic Implemented for Billing Cycles**

* The Billing Cycle drop-down shows a list of months starting from the selected financial year **from Date** month till current date month.
* On selection of the desired month, the billing period value is set from the selected month’s first date to the selected month’s last date. \(Eg. Selected Billing Cycle: June 2021, so Billing period: 01/07/2021 - 30/07/2021\)

### **Files Path**

Primary Files:[ ![](https://github.com/fluidicon.png)punjab-mgramseva/GenerateBill.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/screeens/GenerateBill/GenerateBill.dart)

### **Field Validations**

| **SL** | **Fileds** | **Validations** |
| :--- | :--- | :--- |
| 1 | Billing Year\* | `isMandatory` |
| 2 | Billing Cycle\* | `isMandatory` |

<table>
  <thead>
    <tr>
      <th style="text-align:left"><b>API EndPoint</b>
      </th>
      <th style="text-align:left"><b>Input Params (Modules)</b>
      </th>
      <th style="text-align:left"><b>Description</b>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><code>egov-mdms-service/v1/_search</code>
      </td>
      <td style="text-align:left">
        <p><code>ws-services-masters</code>
        </p>
        <p><code>PropertyTax</code>
        </p>
        <p> <code>BillingService</code>
        </p>
      </td>
      <td style="text-align:left">
        <p>To Fetch the Details of</p>
        <ul>
          <li><code>connectionType</code> from <code>ws-services-masters</code>
          </li>
          <li><code>TaxPeriod</code> from <code>BillingService</code> where <code>service==&apos;WS&apos; &amp;&amp; @.fromDate &lt;= $datestamp &amp;&amp; @.toDate &gt;= $datestamp</code>
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

### **API Details**

| **SL** | **End Point** | **Request Method** | **Request Info** |
| :--- | :--- | :--- | :--- |
| 1 | `/ws-calculator/waterCalculator/_bulkDemand` | `POST` | "tenantId": {}, "billingPeriod": {} |

#### **Stack**

1 → Home Screen. + Generate Bulk Demand Screen

Pop → Home Screen

Widgets Utilised from Library

<table>
  <thead>
    <tr>
      <th style="text-align:left"><b>SL No</b>
      </th>
      <th style="text-align:left"><b>Widgets</b>
      </th>
      <th style="text-align:left"><b>File Path</b>
      </th>
      <th style="text-align:left"><b>Description</b>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">1</td>
      <td style="text-align:left">
        <ul>
          <li><code>SelectFieldBuilder</code>
          </li>
        </ul>
        <p><b>(Primary File)</b>
        </p>
        <ul>
          <li><code>SearchSelectFieldBuilder</code>
          </li>
        </ul>
        <p><b>(Secondary File)</b>
        </p>
      </td>
      <td style="text-align:left">
        <p><a href="https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/widgets/SelectFieldBuilder.dart"><img src="https://github.com/fluidicon.png" alt/>punjab-mgramseva/SelectFieldBuilder.dart at develop &#xB7; egovernments/punjab-mgramseva</a>
        </p>
        <p><a href="https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/widgets/SearchSelectFieldBuilder.dart"><img src="https://github.com/fluidicon.png" alt/>punjab-mgramseva/SearchSelectFieldBuilder.dart at develop &#xB7; egovernments/punjab-mgramseva</a>
        </p>
      </td>
      <td style="text-align:left">Searchable Dropdown</td>
    </tr>
    <tr>
      <td style="text-align:left">2</td>
      <td style="text-align:left"><code>CommonSuccessPage</code>
      </td>
      <td style="text-align:left"><a href="https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/widgets/CommonSuccessPage.dart"><img src="https://github.com/fluidicon.png" alt/>punjab-mgramseva/CommonSuccessPage.dart at develop &#xB7; egovernments/punjab-mgramseva</a>
      </td>
      <td style="text-align:left">Success Screen</td>
    </tr>
    <tr>
      <td style="text-align:left">3</td>
      <td style="text-align:left"><code>BottomButtonBar</code>
      </td>
      <td style="text-align:left"><a href="https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/widgets/BottonButtonBar.dart"><img src="https://github.com/fluidicon.png" alt/>punjab-mgramseva/BottonButtonBar.dart at develop &#xB7; egovernments/punjab-mgramseva</a>
      </td>
      <td style="text-align:left">Button</td>
    </tr>
  </tbody>
</table>

## Bill Generation - Metered

### **Link**

→ {base url}/mgramseva/home/householddetails/billgenerate.

![](../../../../.gitbook/assets/image%20%2872%29.png)

Users are redirected to the Generate New Bill screen if they click the Generate New Bill option in the household detail screen.

### **Default Values Set**

* The service category defaults to water charges
* The service type defaults to metered connection
* The property type defaults to the selected property type of the consumer

### **User Interaction on Screen**

* Previous Meter Reading: Takes input from the user only for first time Bill generation and if the Previous meter reading is null, else it's defaulted if the meter reading is present.
* New Meter Reading: Takes input from the user
* Meter Reading Date: Defaulted to today’s date, the User can change it to the desired date.

### **User Interaction on Bill Generation Success Screen**![](blob:https://digit-discuss.atlassian.net/e0b51049-9047-4cf5-aff1-355c808cead2#media-blob-url=true&id=93f529e2-0f5b-45fc-a5cd-1b8e9cf857d8&collection=contentId-1925480514&contextId=1925480514&mimeType=image%2Fpng&name=Bill%20Success.png&size=48696&width=378&height=815&alt=)

* Users have the option of downloading the bill or sharing it via Whatsapp
* On click of the Collect Payment button, the user is navigated to the Payment Screen

### **Files Path**

Primary Files:[ ![](https://github.com/fluidicon.png)punjab-mgramseva/GenerateBill.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/screeens/GenerateBill/GenerateBill.dart)

### **Field Validations**

<table>
  <thead>
    <tr>
      <th style="text-align:left"><b>SL</b>
      </th>
      <th style="text-align:left"><b>Fileds</b>
      </th>
      <th style="text-align:left"><b>Validations</b>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">1</td>
      <td style="text-align:left">Previous Meter Reading*</td>
      <td style="text-align:left">
        <ul>
          <li><code>r&apos;^[0-9]+$&apos;</code>
          </li>
          <li><code>5 - digit reading</code>
          </li>
          <li> <code>if Meter Reading &lt; 5 digit, prepend zeroes</code>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">2</td>
      <td style="text-align:left">New Meter Reading*</td>
      <td style="text-align:left">
        <ul>
          <li><code>r&apos;^[0-9]+$&apos;</code>
          </li>
          <li><code>5 - digit reading</code>
          </li>
          <li> <code>if Meter Reading &lt; 5 digit, prepend zeroes</code>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">3</td>
      <td style="text-align:left">Meter Reading Date*</td>
      <td style="text-align:left">
        <ul>
          <li> <code>Shows dates till today&apos;s date</code>
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

<table>
  <thead>
    <tr>
      <th style="text-align:left"><b>API EndPoint</b>
      </th>
      <th style="text-align:left"><b>Input Params (Modules)</b>
      </th>
      <th style="text-align:left"><b>Description</b>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><code>egov-mdms-service/v1/_search</code>
      </td>
      <td style="text-align:left">
        <p><code>ws-services-masters</code>
        </p>
        <p><code>PropertyTax</code>
        </p>
        <p> <code>BillingService</code>
        </p>
      </td>
      <td style="text-align:left">
        <p>To Fetch the Details of</p>
        <ul>
          <li><code>connectionType</code> from <code>ws-services-masters</code>
          </li>
          <li><code>PropertyType</code> from <code>PropertyTax</code>
          </li>
          <li><code>TaxHeadMaster</code> from <code>BillingService</code> where <code>service==&apos;WS&apos;</code>
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

### **API Details**

<table>
  <thead>
    <tr>
      <th style="text-align:left"><b>SL</b>
      </th>
      <th style="text-align:left"><b>End Point</b>
      </th>
      <th style="text-align:left"><b>Request Method</b>
      </th>
      <th style="text-align:left"><b>Request Info</b>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">1</td>
      <td style="text-align:left"><code>/ws-calculator/meterConnection/_create</code>
      </td>
      <td style="text-align:left"><code>POST</code>
      </td>
      <td style="text-align:left">
        <p>&quot;meterReadings&quot;: {
          <br />&quot;currentReading&quot;: {},
          <br />&quot;currentReadingDate&quot;: {},
          <br />&quot;billingPeriod&quot;: {},
          <br />&quot;meterStatus&quot;: &quot;Working&quot;,
          <br />&quot;connectionNo&quot;: {},
          <br />&quot;lastReading&quot;: {},
          <br />&quot;lastReadingDate&quot;: {},
          <br />&quot;generateDemand&quot;: true,
          <br />&quot;tenantId&quot;: {}</p>
        <p>}</p>
      </td>
    </tr>
  </tbody>
</table>

#### **Stack**

1 → Home Screen + Household Details Screen + Generate Bill Metered

Pop → Household Details Screen

Widgets Utilised from Library

<table>
  <thead>
    <tr>
      <th style="text-align:left"><b>SL No</b>
      </th>
      <th style="text-align:left"><b>Widgets</b>
      </th>
      <th style="text-align:left"><b>File Path</b>
      </th>
      <th style="text-align:left"><b>Description</b>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">1</td>
      <td style="text-align:left">
        <ul>
          <li><code>MeterReading</code>
          </li>
        </ul>
      </td>
      <td style="text-align:left"><a href="https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/screeens/GenerateBill/widgets/MeterReading.dart"><img src="https://github.com/fluidicon.png" alt/>punjab-mgramseva/MeterReading.dart at develop &#xB7; egovernments/punjab-mgramseva</a>
      </td>
      <td style="text-align:left">Meter Reading 5 digit boxes field</td>
    </tr>
    <tr>
      <td style="text-align:left">2</td>
      <td style="text-align:left">
        <ul>
          <li><code>SelectFieldBuilder</code>
          </li>
        </ul>
        <p><b>(Primary File)</b>
        </p>
        <ul>
          <li><code>SearchSelectFieldBuilder</code>
          </li>
        </ul>
        <p><b>(Secondary File)</b>
        </p>
      </td>
      <td style="text-align:left">
        <p><a href="https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/widgets/SelectFieldBuilder.dart"><img src="https://github.com/fluidicon.png" alt/>punjab-mgramseva/SelectFieldBuilder.dart at develop &#xB7; egovernments/punjab-mgramseva</a>
        </p>
        <p><a href="https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/widgets/SearchSelectFieldBuilder.dart"><img src="https://github.com/fluidicon.png" alt/>punjab-mgramseva/SearchSelectFieldBuilder.dart at develop &#xB7; egovernments/punjab-mgramseva</a>
        </p>
      </td>
      <td style="text-align:left">Searchable Drop down</td>
    </tr>
    <tr>
      <td style="text-align:left">3</td>
      <td style="text-align:left"><code>DatePickerFieldBulder</code>
      </td>
      <td style="text-align:left"><a href="https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/widgets/DatePickerFieldBuilder.dart"><img src="https://github.com/fluidicon.png" alt/>punjab-mgramseva/DatePickerFieldBuilder.dart at develop &#xB7; egovernments/punjab-mgramseva</a>
      </td>
      <td style="text-align:left">Date Picker</td>
    </tr>
    <tr>
      <td style="text-align:left">4</td>
      <td style="text-align:left"><code>CommonSuccessPage</code>
      </td>
      <td style="text-align:left"><a href="https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/widgets/CommonSuccessPage.dart"><img src="https://github.com/fluidicon.png" alt/>punjab-mgramseva/CommonSuccessPage.dart at develop &#xB7; egovernments/punjab-mgramseva</a>
      </td>
      <td style="text-align:left">Success Screen</td>
    </tr>
    <tr>
      <td style="text-align:left">5</td>
      <td style="text-align:left"><code>BottomButtonBar</code>
      </td>
      <td style="text-align:left"><a href="https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/widgets/BottonButtonBar.dart"><img src="https://github.com/fluidicon.png" alt/>punjab-mgramseva/BottonButtonBar.dart at develop &#xB7; egovernments/punjab-mgramseva</a>
      </td>
      <td style="text-align:left">Button</td>
    </tr>
  </tbody>
</table>

