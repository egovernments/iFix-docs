# Search Connection

## **Link** 

→ {base url}/mgramseva/home/householdSearch?Mode=collect

 → {base url}/mgramseva/home/consumersearchupdate?Mode=update

 → {base url}/mgramseva/home/householdReceiptsSearch?Mode=receipts

![](../../../../.gitbook/assets/image%20%2884%29.png)

Users are redirected to this screen once they click on the Collect Payment Card or the Update Consumer Details Card or Download Bills and Receipts Card on Home Screen.![](blob:https://digit-discuss.atlassian.net/23527a1c-0ba9-4b83-9c8f-ae1824f6554a#media-blob-url=true&id=22a4929f-89bc-480a-a918-c5a4e85188ab&collection=contentId-1925316787&contextId=1925316787&mimeType=image%2Fpng&name=Search%20Connection.png&size=43384&width=380&height=814&alt=)

## **User Interaction on Screen**

* Users can search the consumer/connection with their Mobile Number / Name / Old Connection ID / New Connection ID \( `Search with any one of these`\)
* Click on Search to get the household details of the Consumer/Connection

## **Files Path**

Primary Files:[ ![](https://github.com/fluidicon.png)punjab-mgramseva/SearchConnection.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/screeens/ConnectionResults/SearchConnection.dart)

## **Field Validations**

| **SL** | **Fileds** | **Validations** |
| :--- | :--- | :--- |
| 1 | Owner Mobile Number | `r'^(?:[+0]9)?[0-9]{10}$'` |
| 2 | Name of the Consumer | `r'^[A-Za-z ]'` |
| 3 | Old Connection ID | `No Validation` |
| 4 | New Connection ID | `No Validation` |

## **API Details**

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
      <td style="text-align:left"><code>/ws-services/wc/_search</code>
      </td>
      <td style="text-align:left"><code>POST</code>
      </td>
      <td style="text-align:left">
        <p>tenantId: {}</p>
        <p>oldConnectionNumber: {}</p>
        <p>name: {}</p>
        <p>connectionNumber: {}</p>
        <p>mobileNumber: {}</p>
      </td>
    </tr>
  </tbody>
</table>

### Stack

1 → Home Screen. + Search Connection Screen

Pop → Home Screen

Widgets Utilised from Library

| **SL No** | **Widgets** | **File Path** | **Description** |
| :--- | :--- | :--- | :--- |
| 1 | `BuildTextField` | [![](https://github.com/fluidicon.png)punjab-mgramseva/TextFieldBuilder.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/widgets/TextFieldBuilder.dart) | Text Field |
| 2 | `BottomButtonBar` | [![](https://github.com/fluidicon.png)punjab-mgramseva/BottonButtonBar.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/widgets/BottonButtonBar.dart) | Button |

