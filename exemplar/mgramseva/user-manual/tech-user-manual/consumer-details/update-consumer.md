# Update Consumer

Enables employees to update consumer details.

![](../../../../../.gitbook/assets/image%20%2879%29.png)

Users are redirected to this screen/page when they click on the Update Consumer Details card

![](../../../../../.gitbook/assets/image%20%2869%29.png)

## **Link** 

→ {base url}/mgramseva/home/consumersearchupdate?Mode=update

 → {base url}/mgramseva/home/consumersearchresult

It redirects to [Search Connection](https://digit-discuss.atlassian.net/wiki/spaces/DD/pages/1925316787) Page in `update` mode where users enter specific consumer details to search for consumers. The search result screen has the Edit Consumer button. Clicking on this button navigates the users to the Update Consumer screen.

## **Field Validations**

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
| 9 | Property Type\* | None |
| 10 | Service Type\* | None |
| 11 | Meter Id | `[a-zA-Z0-9]` |
| 12 | Meter Reading | `[0-9]` |
| 13 | Billing Cycle | None |
| 14 | Arrears | `[0-9.]` |

{% hint style="info" %}
**Note**: All fields are validated on Submit apart from the phone number which gets validated on change.
{% endhint %}

## **API Details**

| **SL** | **API** | **Params** | **Description** |
| :--- | :--- | :--- | :--- |
| 1 | `/egov-mdms-service/v1/_search` | `[{"moduleName":"ws-services-masters","masterDetails":[{"name":"connectionType"}]},{"moduleName":"PropertyTax","masterDetails":[{"name":"PropertyType"}]},{"moduleName":"BillingService","masterDetails":[{"name":"TaxPeriod","filter":"[?(@.service=='WS' && @.fromDate <= 1631989800000 && @.toDate >= 1631989800000)]` | To get the Property Type and service Type and billing cycle values for the Dropdown |
| 2 | `egov-location/location/v11/boundarys/_search?` | `hierarchyTypeCode=REVENUE&boundaryType=Locality&tenantId={tenantID}` | To get the values for Locality DropDow |
| 3 | `billing-service/demand/_search` | `consumerCode`, `businessService`, `tenantId` | To Fetch Demand Details |
| 4 | `property-services/property/_search` | `propertyIds`, `tenantId` | To Fetch Property Type |
| 5 | `ws-services/wc/_search` | `connectionNumber`, `tenantId` | On Demand this API is Made |

Components utilised from **Widgets Library**

| **SL** | **Components** | **File Path** |
| :--- | :--- | :--- |
| 1 | TextField Builder | [![](https://github.com/fluidicon.png)punjab-mgramseva/TextFieldBuilder.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/widgets/TextFieldBuilder.dart) |
| 2 | RadioButtonField Builder | [![](https://github.com/fluidicon.png)punjab-mgramseva/RadioButtonFieldBuilder.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/widgets/RadioButtonFieldBuilder.dart) |
| 3 | SearchSelectField Builder | [![](https://github.com/fluidicon.png)punjab-mgramseva/SearchSelectFieldBuilder.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/widgets/SearchSelectFieldBuilder.dart) |
| 4 | DatePicker Builder | [![](https://github.com/fluidicon.png)punjab-mgramseva/DatePickerFieldBuilder.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/widgets/DatePickerFieldBuilder.dart) |



