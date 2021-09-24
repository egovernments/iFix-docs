# Search Expense Bills

## **Link**

→ {base url}/mgramseva/home/searchExpense

![](../../../../../.gitbook/assets/image%20%2894%29.png)

Users are redirected to this screen by selecting the Update Expense card on the home screen.![](blob:https://digit-discuss.atlassian.net/c8e3382f-6264-4770-989f-b8c80f5976f0#media-blob-url=true&id=7e42a741-9da9-4bfc-879b-2bbafa70c5a7&collection=contentId-1926791391&contextId=1926791391&mimeType=image%2Fpng&name=Search%20EXpense.png&size=42495&width=373&height=806&alt=)

Update Expenses card is available on the home screen for defined roles that have EXPENSE PROCESSING permission.

## **User Interaction on Screen**

* Users can search the expense bills with the Vendor Name / Type of Expense / Bill ID \( `Search with any one of these criteria` \)
* Click on Search navigates the user to the expense results screen which lists the expenditure bills matching the search criteria.

## **Files Path**

Primary Files:

[ ![](https://github.com/fluidicon.png)punjab-mgramseva/search\_expense.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/screeens/expense/search_expense.dart) 

[![](https://github.com/fluidicon.png)punjab-mgramseva/expense\_results.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/screeens/expense/expense_results.dart)

![](../../../../../.gitbook/assets/image%20%2893%29.png)

## **Field Validations**

| **SL** | **Fileds** | **Validations** |
| :--- | :--- | :--- |
| 1 | Owner Mobile Number | `r'^(?:[+0]9)?[0-9]{10}$'` |
| 2 | Name of the Consumer | `r'^[A-Za-z ]'` |
| 3 | Old Connection ID | `No Validation` |
| 4 | New Connection ID | `No Validation` |

## **API Details**

| **SL** | **API** | **Params** | **Description** |
| :--- | :--- | :--- | :--- |
| 1 | `/egov-mdms-service/v1/_search` | `[{"moduleName": "Expense", "masterDetails": [{"name": "ExpenseType"},]}, {"moduleName": "BillingService", "masterDetails": [{"name": "BusinessService"}, {"name": "TaxHeadMaster"},]}]` | To get the Expense Type for the Dropdown |

### Stack

1 → Home Screen. + Search Expense Bills Screen

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
      <td style="text-align:left"><code>BuildTextField</code>
      </td>
      <td style="text-align:left"><a href="https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/widgets/TextFieldBuilder.dart"><img src="https://github.com/fluidicon.png" alt/>punjab-mgramseva/TextFieldBuilder.dart at develop &#xB7; egovernments/punjab-mgramseva</a>
      </td>
      <td style="text-align:left">Text Field</td>
    </tr>
    <tr>
      <td style="text-align:left">2</td>
      <td style="text-align:left">
        <ul>
          <li>
            <br /><code>SelectFieldBuilder</code>
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
      <td style="text-align:left"><code>BottomButtonBar</code>
      </td>
      <td style="text-align:left"><a href="https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/widgets/BottonButtonBar.dart"><img src="https://github.com/fluidicon.png" alt/>punjab-mgramseva/BottonButtonBar.dart at develop &#xB7; egovernments/punjab-mgramseva</a>
      </td>
      <td style="text-align:left">Button</td>
    </tr>
  </tbody>
</table>

