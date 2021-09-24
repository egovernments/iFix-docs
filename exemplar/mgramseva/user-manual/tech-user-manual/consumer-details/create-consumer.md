# Create Consumer

Provides Employees to create Consumer/Connection - Process of Onboarding the End Users.

## **Link**

→ {base url}/mgramseva/home/consumercreate.

![](../../../../../.gitbook/assets/image%20%2871%29.png)

Create Consumer card is available on the home screen as per the defined user role.

Click on the Consumer Create card navigates the user to the consumer creation screen.

Users enter the required details for the creation of Consumer.

If a user logs in for the first time then a walkthrough is populated following the same logic as in the home screen.

## File Path

Primary Files -[ ![](https://github.com/fluidicon.png)punjab-mgramseva/WalkFlowContainer.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/screeens/ConsumerDetails/ConsumerDetailsWalkThrough/WalkFlowContainer.dart) ,[ ![](https://github.com/fluidicon.png)punjab-mgramseva/walkthrough.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/screeens/ConsumerDetails/ConsumerDetailsWalkThrough/walkthrough.dart)

| **SL** | **Fields** | **Validations** |
| :--- | :--- | :--- |
| 1 | consumer Name\* | `[A-Za-z ]` |
| 2 | Gender\* | None |
| 3 | Spouse/Parent’s Name\* | `[A-Za-z ]` |
| 4 | Phone Number\* | `[0-9]` |
| 5 | Old Connection No | None |
| 6 | Door Number | None |
| 7 | Street Name/Number | None |
| 8 | Gram Panchayat Name\* | None- Disabled |
| 9 | Propert Type\* | None |
| 10 | Service Type\* | None |
| 11 | Meter Id | `[a-zA-Z0-9]` |
| 12 | Meter Reading | `[0-9]` |
| 13 | Billing Cycle | None |
| 14 | Arrears | `[0-9.]` |

{% hint style="info" %}
**Note**: All fields are validated on Submit except the Phone number which gets validated on change.
{% endhint %}

## **API details**

| **SL** | **API** | **Params** | **Description** |
| :--- | :--- | :--- | :--- |
| 1 | `/egov-mdms-service/v1/_search` | `[{"moduleName":"ws-services-masters","masterDetails":[{"name":"connectionType"}]},{"moduleName":"PropertyTax","masterDetails":[{"name":"PropertyType"}]},{"moduleName":"BillingService","masterDetails":[{"name":"TaxPeriod","filter":"[?(@.service=='WS' && @.fromDate <= 1631989800000 && @.toDate >= 1631989800000)]` | To get the Property Type and service Type and billing cycle values for the Dropdown |
| 2 | `egov-location/location/v11/boundarys/_search?` | `hierarchyTypeCode=REVENUE&boundaryType=Locality&tenantId={tenantID}` | To get the values for Locality DropDow |

Consumer creation involves 2 sequential Process

1. Property Creation
2. Water connection Creation

After creating a property, the Property ID is linked to the WaterConnection Request JSON.

Water connection creation is of two types:

A metered connection that requires Meter ID and meter installation Date/ Last Meter Reading Date and an optional field to capture meter reading**.**

![](../../../../../.gitbook/assets/image%20%2879%29.png)

Non-Metered Connection which requires the last billing cycle as mandatory params captured in the field as shown below.

![](../../../../../.gitbook/assets/image%20%2884%29.png)

 Users can switch between connection types by selecting a desired value from the **Service Type** DropDown.

![](../../../../../.gitbook/assets/image%20%2862%29.png)

<table>
  <thead>
    <tr>
      <th style="text-align:left"><b>SL</b>
      </th>
      <th style="text-align:left"><b>API</b>
      </th>
      <th style="text-align:left"><b>Description</b>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">1</td>
      <td style="text-align:left"><code>property-services/property/_create</code>
      </td>
      <td style="text-align:left">
        <p>Property Creation Request JSON</p>
        <p>defined in<a href="https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/model/connection/property.dart"> <img src="https://github.com/fluidicon.png" alt/>punjab-mgramseva/property.dart at develop &#xB7; egovernments/punjab-mgramseva</a>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">2</td>
      <td style="text-align:left"><code>ws-services/wc/_create</code>
      </td>
      <td style="text-align:left">Water Connection Request JSON defined in<a href="https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/model/connection/water_connection.dart"> <img src="https://github.com/fluidicon.png" alt/>punjab-mgramseva/water_connection.dart at develop &#xB7; egovernments/punjab-mgramseva</a>
      </td>
    </tr>
  </tbody>
</table>

##  **Role Access Mapping**

```text
    case Routes.CONSUMER_CREATE:
        return ['GP_ADMIN', 'SUPERUSER'];
```

Components utilised from **Widgets Library**

| **SL** | **Components** | **File Path** |
| :--- | :--- | :--- |
| 1 | TextField Builder | [![](https://github.com/fluidicon.png)punjab-mgramseva/TextFieldBuilder.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/widgets/TextFieldBuilder.dart) |
| 2 | RadioButtonField Builder | [![](https://github.com/fluidicon.png)punjab-mgramseva/RadioButtonFieldBuilder.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/widgets/RadioButtonFieldBuilder.dart) |
| 3 | SearchSelectField Builder | [![](https://github.com/fluidicon.png)punjab-mgramseva/SearchSelectFieldBuilder.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/widgets/SearchSelectFieldBuilder.dart) |
| 4 | DatePicker Builder | [![](https://github.com/fluidicon.png)punjab-mgramseva/DatePickerFieldBuilder.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/widgets/DatePickerFieldBuilder.dart) |

## **Files Path**

Model →[ ![](https://github.com/fluidicon.png)punjab-mgramseva/property.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/model/connection/property.dart) ,[ ![](https://github.com/fluidicon.png)punjab-mgramseva/water\_connection.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/model/connection/water_connection.dart)

View →[ ![](https://github.com/fluidicon.png)punjab-mgramseva/ConsumerDetails.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/screeens/ConsumerDetails/ConsumerDetails.dart)

Controller →[ ![](https://github.com/fluidicon.png)punjab-mgramseva/consumer\_details\_repo.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/repository/consumer_details_repo.dart) ,[ ![](https://github.com/fluidicon.png)punjab-mgramseva/consumer\_details\_provider.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/providers/consumer_details_provider.dart)

