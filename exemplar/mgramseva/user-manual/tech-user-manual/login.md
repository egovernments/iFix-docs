# Login

## **Link**

→ {base url}/mgramseva/selectLanguage/login

![](../../../../.gitbook/assets/image%20%2859%29.png)

Users are redirected to this screen once they select the preferred language in the previous screen

## **User Interaction on Screen**

* Users enter the registered Phone Number and Password.
* Click on Continue.
* First-time login users navigate to Reset Password Page.

**Log in with the default password**

YES → [Reset Password/ Update Password Screen](https://digit-discuss.atlassian.net/wiki/spaces/DD/pages/1922662535)

NO → [Home Screen](https://digit-discuss.atlassian.net/wiki/spaces/DD/pages/1923416085)

## **Files Path**

Primary Files[ ![](https://github.com/fluidicon.png)punjab-mgramseva/Login.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/screeens/Login/Login.dart)

## **Field Validations**

| **SL** | **Fileds** | **Validations** |
| :--- | :--- | :--- |
| 1 | Phone Number\* | `r'^[0-9]+$'` |
| 2 | Password\* | `r'^(?=.*?[A-Za-z])(?=.*?[0-9])(?=.*?[#?!@$%^&*-]).{6,}$'` |

## API details

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
      <td style="text-align:left"><code>/user/oauth/token</code>
      </td>
      <td style="text-align:left"><code>POST</code>
      </td>
      <td style="text-align:left">
        <p>username: {}</p>
        <p>password:{}</p>
        <p>scope: read</p>
        <p>grant_type: password</p>
        <p>tenantId: {}</p>
        <p>userType: EMPLOYEE</p>
      </td>
    </tr>
  </tbody>
</table>

### **Stack**

1 → Language Selection Screen. + Login Screen.

Pop → Language Selection Screen.

Widgets Utilised from Library

| **SL No** | **Widgets** | **File Path** | **Description** |
| :--- | :--- | :--- | :--- |
| 1 | `BuildTextField` | [![](https://github.com/fluidicon.png)punjab-mgramseva/TextFieldBuilder.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/widgets/TextFieldBuilder.dart) | Text Field |
| 2 | `Button` | [![](https://github.com/fluidicon.png)punjab-mgramseva/Button.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/widgets/Button.dart) | Button |

