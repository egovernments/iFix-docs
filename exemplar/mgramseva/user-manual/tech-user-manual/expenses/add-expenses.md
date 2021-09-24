# Add Expenses

## **Link**

→ {base url}/mgramseva/home/addExpense

![](../../../../../.gitbook/assets/image%20%2867%29.png)

Enables employees to add expenses - the process of onboarding the end-users![](blob:https://digit-discuss.atlassian.net/6ecd56d9-fd43-4af9-b648-98388e99a418#media-blob-url=true&id=71b2de6b-37fa-413d-9270-4bfab1d1030b&collection=contentId-1926824121&contextId=1926824121&mimeType=image%2Fpng&name=Add%20expense.png&size=37466&width=378&height=813&alt=)

Add Expenses card is available on the home screen for defined user roles having the EXPENSE PROCESSING permission.

Clicking the Add Expense Record tile/card on the home screen navigates the user to Add Expenses screen.

The user enters the required details to add the expenses for the vendors.

If a user logs in for the first time then a walkthrough is populated following the same logic as in the home screen.

Clicking on the Submit button navigates the user to the Expenditure Added Successful acknowledgement screen.

![](../../../../../.gitbook/assets/image%20%2888%29.png)

## **Logic Implemented for Date Validation and File Attachments**

### **File Attachments**

This feature allows the user to take a picture or choose a single file. The [Image Picker](https://pub.dev/packages/image_picker) plugin is used to implementing this.

Whenever this application is used on mobile, it prompts the user with two options - Camera and File Picker. If the application is opened on desktop or laptop browsers, the camera option is not available. The user has to select an image from the folder.

The maximum supported file size is 5 MB.

###  **Date Validation**

For validating the form we use the Form widget. Once the user selects a bill date the Bill Pay option is enabled. Else, the auto validation process is enabled.

Based on the bill date, the party selection date is enabled. If the user selects the party selection date first, the bill date can be selected only after entering the party date.

Whenever the bill paid option is true, the paid date field is enabled and mandatory. The date selection range allows date input only after the bill date and before the current date.

## **File Path**

Primary Files -

[ ![](https://github.com/fluidicon.png)punjab-mgramseva/ExpenseDetails.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/screeens/AddExpense/ExpenseDetails.dart)

 [![](https://github.com/fluidicon.png)punjab-mgramseva/WalkThroughContainer.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/screeens/AddExpense/AddExpenseWalkThrough/WalkThroughContainer.dart) 

[![](https://github.com/fluidicon.png)punjab-mgramseva/expenseWalkThrough.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/screeens/AddExpense/AddExpenseWalkThrough/expenseWalkThrough.dart)

| **SL** | **Fields** | **Validations** |
| :--- | :--- | :--- |
| 1 | Vendor Name\* | `[A-Za-z ]` |
| 2 | Mobile Number\* | `[0-9] & is mandatory only if a new vendor is added` |
| 3 | Type of Expense\* | None |
| 4 | Amount\* | `[0-9]` |
| 5 | Bill Date\* |  Before Current Date and after party Bill Date. |
| 6 | Party Bill Date | `Should be before the Bill Date` |
| 7 | Bill Paid | None |
| 8 | Paid Date |  After Bill date and less than current Date. |
| 9 | Attach Documents | Option to upload a single document, Supported files - PDF, JPEG, PNG \(maximum 5MB\) |

{% hint style="info" %}
**Note:** All fields are validated on Submit apart from the Mobile number which gets validated on change.
{% endhint %}

## **API Details**

| **SL** | **API** | **Params** | **Description** |
| :--- | :--- | :--- | :--- |
| 1 | `/egov-mdms-service/v1/_search` | `[{"moduleName": "Expense", "masterDetails": [{"name": "ExpenseType"},]}, {"moduleName": "BillingService", "masterDetails": [{"name": "BusinessService"}, {"name": "TaxHeadMaster"},]}]` | To get the Expense Type for the Dropdown |
| 2 | `egov.org.in/vendor/v1/_search` | `tenantId: {}` | To get the list of vendors in the selected tenant for the suggestion text box - Vendor Name |

### Stack

1 → Home Screen. + Add Expense Screen

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

