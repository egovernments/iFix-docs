# Expenditure Dashboard

## **Link**

 → {base url}/mgramseva/home/dashboard?tab=1.

![](../../../../../.gitbook/assets/image%20%2892%29.png)

Users are redirected to this screen when they select the GPWSC Dashboard option on the home screen.![](blob:https://digit-discuss.atlassian.net/f7db6b6a-1768-405c-940c-44c83edd1dd0#media-blob-url=true&id=98423659-e86d-4b1a-9a31-c677a3bd6f1f&collection=contentId-1926791281&contextId=1926791281&mimeType=image%2Fpng&name=dashboard_expenditure.PNG&size=32036&width=276&height=484&alt=)

## **User Interaction on Screen**

* Users can select the year from the drop-down which contains the list of financial years.
* From the text field, users can search the expenses using Bill ID or vendor name.
* Users can see the expense data for paid and pending with respective tabs.
* Initially, only 10 expenses are loaded for the selected tab. The pagination dropdown and right arrow click enable the user to load and view more expense records.
* Selecting any Bill ID navigates the users to the [Expense update screen](https://digit-discuss.atlassian.net/wiki/spaces/DD/pages/1927348594).

## **Files Path**

Primary Files:[ ![](https://github.com/fluidicon.png)punjab-mgramseva/Dashboard.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/screeens/dashboard/Dashboard.dart)[ ![](https://github.com/fluidicon.png)punjab-mgramseva/search\_expense.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/screeens/dashboard/search_expense.dart)

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
      <td style="text-align:left">/<code>echallan-services/eChallan/v1/_create</code>
      </td>
      <td style="text-align:left">POST</td>
      <td style="text-align:left">
        <p>tenantId : {}
          <br />offset ; {}
          <br />limit : {}
          <br />fromDate : {}
          <br />toDate : {}
          <br />vendorName : {}
          <br />challanNo : {}
          <br />toDate : {}
          <br />freeSearch : {}
          <br />status : {}
          <br />isBillCount : {}</p>
        <p>sortOrder ; {}
          <br />sortBy : {}
          <br />isBillPaid : {}</p>
      </td>
    </tr>
  </tbody>
</table>

### **Stack**

1 → Home Screen. + Dashboard expenditure screen + update expense screen

Pop → Dashboard expenditure screen → Home Screen

2 → Home Screen. + Dashboard expenditure screen + update expense screen + expense update success

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

\*\*\*\*

## **Files Path**

Model →[ ![](https://github.com/fluidicon.png)punjab-mgramseva/expenses\_details.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/model/expensesDetails/expenses_details.dart)

View →[ ![](https://github.com/fluidicon.png)punjab-mgramseva/Dashboard.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/screeens/dashboard/Dashboard.dart) 

[ ![](https://github.com/fluidicon.png)punjab-mgramseva/search\_expense.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/screeens/dashboard/search_expense.dart)

Controller →[ ![](https://github.com/fluidicon.png)punjab-mgramseva/dashboard\_provider.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/providers/dashboard_provider.dart) 

[![](https://github.com/fluidicon.png)punjab-mgramseva/expenses\_repo.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/repository/expenses_repo.dart)

