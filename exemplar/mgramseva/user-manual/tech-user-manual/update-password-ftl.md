# Update Password FTL

## **Link**

→ {base url}/mgramseva/selectLanguage/login/`updatepassword`

![](../../../../.gitbook/assets/image%20%2875%29.png)

Users are redirected to the Update Password screen once they log in successfully the first time.![](blob:https://digit-discuss.atlassian.net/4ebc458f-348a-475e-afe8-88bf15283ee1#media-blob-url=true&id=a46b0d6c-3c49-44dc-9cfc-aaa7b8106cc3&collection=contentId-1922662535&contextId=1922662535&mimeType=image%2Fpng&name=Screenshot_1632119237.png&size=406069&width=1440&height=3040&alt=)

### **User Interaction on Screen**

* Enter the OTP sent on the user’s 10 digit Mobile Number.
* Set the new password for logging into the application.
* Click on Change Password to apply new password credentials for the user.
* Users can see the allocated Grama Panchayat name and code in the table.

## **Password Hint Card**

* This feature helps to Match with the user’s password and check if the Password contains
  * Minimum 6 digits
  * At least one special character \( !\#$%^&...\)
  * At least one letter
  * At least one number

### **Files Path**

Primary Files[ ![](https://github.com/fluidicon.png)punjab-mgramseva/Updatepassword.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/screeens/ResetPassword/Updatepassword.dart)

## **Logic for Tenant Filtration**

Fetching the tenants from MDMS, based on the user roles in the user request filtering the tenants by comparing tenant Id.

## **Field Validations**

| **SL** | **Fileds** | **Validations** |
| :--- | :--- | :--- |
| 1 | Enter the OTP sent \* | `r'^[0-9]+$'` , 6 digit |
| 2 | Enter a New Password\* | `r'^(?=.*?[A-Za-z])(?=.*?[0-9])(?=.*?[#?!@$%^&*-]).{6,}$'` |
| 3 | Confirm New Password | Match with New Password |

## **API Details**

| **SL** | **End Point** | **Request Method** | **Request Info** |
| :--- | :--- | :--- | :--- |
| 1 | `user/password/nologin/_update` | `POST` | "otpReference": {}, "userName": {}, "newPassword": {}, "tenantId": {}, "type": “Employee” |
| 2 | `egov-mdms-service/v1/_search` | POST | "MdmsCriteria": { "tenantId": tenantId, "moduleDetails": \[ { "moduleName": "tenant", "masterDetails": \[ {"name": "tenants"} \], }, \] } |

### **Stack**

1 → Language Selection Screen. + Login Screen + Update Password + Update password success

Pop → Login

Widgets Utilised from Library

| **SL No** | **Widgets** | **File Path** | **Description** |
| :--- | :--- | :--- | :--- |
| 1 | `BuildTextField` | [![](https://github.com/fluidicon.png)punjab-mgramseva/TextFieldBuilder.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/widgets/TextFieldBuilder.dart) | Text Field |
| 2 | `BottomButtonBar` | [![](https://github.com/fluidicon.png)punjab-mgramseva/BottonButtonBar.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/widgets/BottonButtonBar.dart) | Button |
| 3 | `PasswordHint` | [![](https://github.com/fluidicon.png)punjab-mgramseva/PasswordHint.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/widgets/PasswordHint.dart) | Password Hint Card |

## **Files Path**

View →[ ![](https://github.com/fluidicon.png)punjab-mgramseva/Updatepassword.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/screeens/ResetPassword/Updatepassword.dart)

Controller →[ ![](https://github.com/fluidicon.png)punjab-mgramseva/tendants\_repo.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/repository/tendants_repo.dart)

