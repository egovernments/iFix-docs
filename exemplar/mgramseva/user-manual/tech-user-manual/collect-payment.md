# Collect Payment

## **Link**

 → {base url}/mgramseva/household/details/collectPayment![](blob:https://digit-discuss.atlassian.net/7b871954-91b9-47a8-8250-33a09a1908c8#media-blob-url=true&id=91260146-5080-4158-83af-bae678dca7f3&collection=contentId-1928200243&contextId=1928200243&mimeType=image%2Fpng&name=Collect%20Payment%20Areears.png&size=46493&width=373&height=812&alt=)

![](../../../../.gitbook/assets/image%20%2895%29.png)

After the demand is generated for Metered and non-metered connections or if any arrears are present, the Revenue collector uses this screen to collect payments.  

Collect Payment card is available on the home screen to the user role having `COLLECTION_OPERATOR` permission.

## **User Interaction on Screen**

* Users can pay the total due amount by selecting the Full Amount option below Payment Amount.
* Or, Users can also pay a partial amount by selecting Partial Amount from the Payment Amount options. If Partial Amount is selected, users have to provide the amount that he wants to pay.
* Clicking on Collect Payment navigates the user to the Payment Success screen. The user can download the receipt or share the receipt for the collected amount.

## **Logic Implemented for Arrears Breakup**![](blob:https://digit-discuss.atlassian.net/5555ede1-7e6c-4048-9b53-12270099c765#media-blob-url=true&id=be8bc96e-4523-4574-b3cc-b4d8473e642e&collection=contentId-1928200243&contextId=1928200243&mimeType=image%2Fpng&name=Payment%20Success.png&size=40449&width=374&height=636&alt=)

The Arrears is broken into 'BL\_\(TaxHeadCode\)' which we get from Bill details--&gt;Bill Account details ---&gt; Tax Head Code and the amount of particular arrears is similar to the Bill details--&gt; amount from the Fetch Bill API.

![](../../../../.gitbook/assets/image%20%2869%29.png)

\(`Eg. if there are two bills with tax head codes is 10101 and 10102, then Arrears break up is represented as BL_10101(Water Charges) with the corresponding amount and BL_10102(Water Charges-Arrears) with the corresponding amount`\)

## **Files Path**

Primary Files:[ ![](https://github.com/fluidicon.png)punjab-mgramseva/collect\_payment.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/screeens/common/collect_payment.dart)

## **Field Validations**

| **SL** | **Fields** | **Validations** |
| :--- | :--- | :--- |
| 1 | Payment Amount : Full Amount or Partial Amount | None |
| 2 | Partial Amount \(`If Partial Amount is selected`\) | `r'^[0-9]+$' , Can not be 0 or greater than Full Amount` |
| 3 | Payment Method | None |

## **API Details**

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
      <td style="text-align:left"> <code>[{&quot;moduleName&quot;:&quot;BillingService&quot;,&quot;masterDetails&quot;:[{&quot;name&quot;:&quot;BusinessService&quot;,&quot;filter&quot;:&quot;[?(@.code==&apos;WS&apos;)]&quot;}]}]</code>
      </td>
      <td style="text-align:left">To get the billGeneiURL, Calculation of Water services and collectionModesNotAllowed</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>billing-service/bill/v2/_fetchbill</code>
      </td>
      <td style="text-align:left">
        <p><code>consumerCode : {}</code>
        </p>
        <p><code>businessService : WS</code>
        </p>
        <p><code>tenantId : {}</code>
        </p>
      </td>
      <td style="text-align:left">To fetch the bills of the connection/Consumer</td>
    </tr>
  </tbody>
</table>

### Stack

1 → Home Screen. + Search Connection Screen + Household Results + Household Details Screen + Collect Payment Screen

Pop → Household Details Screen

Widgets Utilised from Library

| **SL No** | **Widgets** | **File Path** | **Description** |
| :--- | :--- | :--- | :--- |
| 1 | `BuildTextField` | [![](https://github.com/fluidicon.png)punjab-mgramseva/TextFieldBuilder.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/widgets/TextFieldBuilder.dart) | Text Field |
| 2 | `BottomButtonBar` | [![](https://github.com/fluidicon.png)punjab-mgramseva/BottonButtonBar.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/widgets/BottonButtonBar.dart) | Button |
| 3 | `RadioButtonField` | [![](https://github.com/fluidicon.png)punjab-mgramseva/RadioButtonFieldBuilder.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/widgets/RadioButtonFieldBuilder.dart) | Radio Buttons for options |



