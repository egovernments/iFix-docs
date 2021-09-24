# Modify Expenses

## **Link**

→ {base url}/mgramseva/home/searchExpense/result/updateExpense![](blob:https://digit-discuss.atlassian.net/dca6f43c-dcb2-4af6-a499-d1ec10370375#media-blob-url=true&id=7c300e66-6b1c-4f70-93e8-464b5c325411&collection=contentId-1927348594&contextId=1927348594&mimeType=image%2Fpng&name=Screenshot%202021-09-20%20at%201.52.54%20AM.png&size=40178&width=328&height=584&alt=)

Enables employees to modify/edit the expenses based on the status of the payment.

![](../../../../../.gitbook/assets/image%20%2874%29.png)

Update Expenses card is visible on the home screen for defined user roles that have EXPENSE PROCESSING permission.

Clicking on the Update Expenditure card in the expense search results screen navigates the user to the Edit Expense Bills screen.

Users can edit the previously populated expense details for the vendors.

Clicking on the Submit button navigates the users to the Modified Expenditure Success screen.

## **Logic Implemented for Paid or Unpaid Bills**

**Use Case1:** When the status is “Unpaid”

Allows modification of all the details except the Bill Id. Users can Mark the Bill as “Cancelled” by checking on the option.

**Use Case2:** When the status is “Paid”

Cannot modify any details. But the users can Mark the Bill as “Cancelled” by checking the option.

![](../../../../../.gitbook/assets/image%20%2881%29.png)

## File Path

Primary Files -[ ![](https://github.com/fluidicon.png)punjab-mgramseva/ExpenseDetails.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/screeens/AddExpense/ExpenseDetails.dart) ,

## **Field Validations**

| **SL** | **Fields** | **Validations** |
| :--- | :--- | :--- |
| 1 | Vendor Name\* | `[A-Za-z ]` |
| 2 | Mobile Number\* | `[0-9] & is mandatory only if a new vendor is added` |
| 3 | Type of Expense\* | None |
| 4 | Amount\* | `[0-9]` |
| 5 | Bill Date\* |  Before Current Date and after party Bill Date. |
| 6 | Party Bill Date | `Should be before the Bill Date` |
| 7 | Bill Paid | None |
| 8 | Paid Date | After Bill date and less than current Date. |
| 9 | Attach Documents | Option to upload a single document, Supported files - PDF, JPEG, PNG \(maximun 5MB\) |
| 10 | Mark this Bill as Cancelled | None |

## **API Details** 

| **SL** | **API** | **Params** | **Description** |
| :--- | :--- | :--- | :--- |
| 1 | `/egov-mdms-service/v1/_search` | `[{"moduleName": "Expense", "masterDetails": [{"name": "ExpenseType"},]}, {"moduleName": "BillingService", "masterDetails": [{"name": "BusinessService"}, {"name": "TaxHeadMaster"},]}]` | To get the Expense Type for the Dropdown |
| 2 | `egov.org.in/vendor/v1/_search` | `tenantId: {}` | To get the list of vendors in the selected tenant for the suggestion text box - Vendor Name |

### Stack

1 → Home Screen. + Search Expense Screen + Expense Results Screen + Edit Expense Bills Screen

Pop → Expense Results Screen

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
      <td style="text-align:left"><code>AutoCompleteView</code>
      </td>
      <td style="text-align:left"><a href="https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/widgets/auto_complete.dart"><img src="https://github.com/fluidicon.png" alt/>punjab-mgramseva/auto_complete.dart at develop &#xB7; egovernments/punjab-mgramseva</a>
      </td>
      <td style="text-align:left">Suggestion Text Field</td>
    </tr>
    <tr>
      <td style="text-align:left">3</td>
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
      <td style="text-align:left">4</td>
      <td style="text-align:left"><code>DatePickerFieldBulder</code>
      </td>
      <td style="text-align:left"><a href="https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/widgets/DatePickerFieldBuilder.dart"><img src="https://github.com/fluidicon.png" alt/>punjab-mgramseva/DatePickerFieldBuilder.dart at develop &#xB7; egovernments/punjab-mgramseva</a>
      </td>
      <td style="text-align:left">Date Picker</td>
    </tr>
    <tr>
      <td style="text-align:left">5</td>
      <td style="text-align:left"><code>CommonSuccessPage</code>
      </td>
      <td style="text-align:left"><a href="https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/widgets/CommonSuccessPage.dart"><img src="https://github.com/fluidicon.png" alt/>punjab-mgramseva/CommonSuccessPage.dart at develop &#xB7; egovernments/punjab-mgramseva</a>
      </td>
      <td style="text-align:left">Success Screen</td>
    </tr>
    <tr>
      <td style="text-align:left">6</td>
      <td style="text-align:left"><code>BottomButtonBar</code>
      </td>
      <td style="text-align:left"><a href="https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/widgets/BottonButtonBar.dart"><img src="https://github.com/fluidicon.png" alt/>punjab-mgramseva/BottonButtonBar.dart at develop &#xB7; egovernments/punjab-mgramseva</a>
      </td>
      <td style="text-align:left">Button</td>
    </tr>
  </tbody>
</table>

