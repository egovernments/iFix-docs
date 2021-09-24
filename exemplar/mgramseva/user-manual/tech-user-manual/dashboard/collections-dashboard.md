# Collections Dashboard

## **Link**

 → {base url}/mgramseva/home/dashboard?tab=0.

![](../../../../../.gitbook/assets/image%20%2873%29.png)

Users are redirected to this screen if they select the GPWSC Dashboard option on the home screen.![](blob:https://digit-discuss.atlassian.net/4f1fdd66-faab-4f6e-84a9-1c7e8084276f#media-blob-url=true&id=bc06571f-35c3-4599-b4b8-f0216bf41c68&collection=contentId-1926824058&contextId=1926824058&mimeType=image%2Fpng&name=dashboard_collections.PNG&size=30468&width=272&height=484&alt=)

## **User Interaction on Screen**

* Users can select the year from the drop-down which contains the list of financial years.
* From the text field, users can search connections by using connection ID.
* Users can see the connections data based on the property type for each respective tab \(Ex: All, Residential, Commercial\).
* Initially, only 10 connections are loaded for the selected tab. The pagination dropdown and right arrow click enable users to view more connections.
* By selecting any connection ID users are navigated to the [Connection update screen](https://digit-discuss.atlassian.net/wiki/spaces/DD/pages/1926791195).

## **Files Path**

Primary Files: 

[ ![](https://github.com/fluidicon.png)punjab-mgramseva/Dashboard.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/screeens/dashboard/Dashboard.dart)

[ ![](https://github.com/fluidicon.png)punjab-mgramseva/search\_expense.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/screeens/dashboard/search_expense.dart)

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
      <td style="text-align:left">/<code>ws-services/wc/_search</code>
      </td>
      <td style="text-align:left">POST</td>
      <td style="text-align:left">
        <p>tenantId : {}
          <br />offset ; {}
          <br />limit : {}
          <br />fromDate : {}
          <br />toDate : {}
          <br /><code>iscollectionAmount</code>: {}
          <br /><code>isPropertyCount</code>: {}
          <br /><code>propertyType</code>: {}
          <br /><code>connectionNumber</code>: {}
          <br /><code>freeSearch</code>: {}</p>
        <p>sortOrder ; {}
          <br />sortBy : {}</p>
      </td>
    </tr>
  </tbody>
</table>

### **Stack**

1 → Home Screen. + Dashboard collection screen + update connection screen

Pop → Dashboard collection screen → Home Screen

2 → Home Screen. + Dashboard collection screen + update connection screen + Update Success

Pop → Home Screen

Widgets Utilised from Library

| **SL No** | **Widgets** | **File Path** | **Description** |
| :--- | :--- | :--- | :--- |
| 1 | `Pagination` | [![](https://github.com/fluidicon.png)punjab-mgramseva/pagination.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/widgets/pagination.dart) | Pagination |
| 2 | `BuildTextField` | [![](https://github.com/fluidicon.png)punjab-mgramseva/TextFieldBuilder.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/widgets/TextFieldBuilder.dart) | Text Field |
| 3 | `BillsTable` | [![](https://github.com/fluidicon.png)punjab-mgramseva/BillsTable.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/components/Dashboard/BillsTable.dart) | Table |
| 4 | `LabelText` | [![](https://github.com/fluidicon.png)punjab-mgramseva/LabelText.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/widgets/LabelText.dart) | Subtitle |

## **Role Access Mapping**

```text
case Routes.DASHBOARD:
  return ['SUPERUSER', 'DASHBOARD_VIEWER'];
```

## **Files Path**

Model →[ ![](https://github.com/fluidicon.png)punjab-mgramseva/water\_connections.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/model/connection/water_connections.dart)

View →[ ![](https://github.com/fluidicon.png)punjab-mgramseva/Dashboard.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/screeens/dashboard/Dashboard.dart) ,[ ![](https://github.com/fluidicon.png)punjab-mgramseva/search\_expense.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/screeens/dashboard/search_expense.dart)

Controller →[ ![](https://github.com/fluidicon.png)punjab-mgramseva/dashboard\_provider.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/providers/dashboard_provider.dart) ,[![](https://github.com/fluidicon.png)punjab-mgramseva/search\_connection\_repo.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/repository/search_connection_repo.dart)

