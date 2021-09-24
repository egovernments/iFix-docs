# Forgot Password

Users are redirected to this screen if they click on the Forgot Password link on the home screen.

![](../../../../.gitbook/assets/image%20%2868%29.png)

## **OTP Request**![](blob:https://digit-discuss.atlassian.net/ea9bdc8b-ca2e-466f-b4dc-e230cdcd8833#media-blob-url=true&id=842d8496-309a-430b-86bd-19f136d4b017&collection=contentId-1922728099&contextId=1922728099&mimeType=image%2Fpng&name=Screenshot%202021-09-16%20at%202.02.25%20AM.png&size=113713&width=328&height=580&alt=)

This feature allows users to request OTP by entering a valid \(the registered\) mobile number.

Follow the steps below to set a new password -

* Click on the Forgot Password link visible on the login screen
* Enter a valid mobile number

Other steps are explained in the Reset Password Section.

### **Files Path**

Primary Files[ ![](https://github.com/fluidicon.png)punjab-mgramseva/ForgotPassword.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/screeens/ForgotPassword/ForgotPassword.dart)

### **Field Validation**

| **SL** | **Fields** | **Validation** |
| :--- | :--- | :--- |
| 1 | Phone Number\* | `r'^[0-9]+$'` |

### **API Details**

| **SL** | **End Point** | **Request Method** | **Request Info** |
| :--- | :--- | :--- | :--- |
| 1 | `user-otp/v1/_send` | `POST` | "otp": { "mobileNumber": {}, "tenantId": {}, "type": "passwordreset", "userType": "Employee" } |

#### **Stack**

2 → Language Selection Screen. + Login Screen + ForgotPassword

Pop → Login Screen Screen.

 Widgets Utilised from Library

| **SL No** | **Widgets** | **File Path** | **Description** |
| :--- | :--- | :--- | :--- |
| 1 | `BuildTextField` | [![](https://github.com/fluidicon.png)punjab-mgramseva/TextFieldBuilder.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/widgets/TextFieldBuilder.dart) | Text Field |
| 2 | `Button` | [![](https://github.com/fluidicon.png)punjab-mgramseva/Button.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/widgets/Button.dart) | Button |

## Reset Password

### **Link**

→ {base url}/mgramseva/selectLanguage/login/forgotPassword/resetPassword.

![](../../../../.gitbook/assets/image%20%2871%29.png)

Users are redirected to this screen if they click on the Continue button on Forgot Password screen.![](blob:https://digit-discuss.atlassian.net/c66daa8d-7438-4ae7-b673-b2010ba3fc31#media-blob-url=true&id=808f425b-2032-4943-96ea-53a8f39c452a&collection=contentId-1922728099&contextId=1922728099&mimeType=image%2Fpng&name=Reset%20Password.png&size=96701&width=377&height=813&alt=)

### **User Interaction on Screen**

* Enter the OTP sent on the user’s 10 digit Mobile Number.
* Set the new password for logging into the application.
* Click on Change Password to apply new password credentials for the user.

### **Password Hint Card**

* This feature helps to provide the users with a clear indication of what the password should contain. Acceptable passwords must contain -
  * Minimum 6 digits
  * At least one special character \( !\#$%^&...\)
  * At least one letter
  * At least one number

### **Files Path**

Primary Files[ ![](https://github.com/fluidicon.png)punjab-mgramseva/Resetpassword.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/screeens/ResetPassword/Resetpassword.dart)

### **Field Validations**

| **SL** | **Fileds** | **Validations** |
| :--- | :--- | :--- |
| 1 | Enter the OTP sent \* | `r'^[0-9]+$'` , 6 digit |
| 2 | Enter a New Password\* | `r'^(?=.*?[A-Za-z])(?=.*?[0-9])(?=.*?[#?!@$%^&*-]).{6,}$'` |
| 3 | Confirm New Password | Match with New Password |

### **API Details**

| **SL** | **End Point** | **Request Method** | **Request Info** |
| :--- | :--- | :--- | :--- |
| 1 | `user/password/nologin/_update` | `POST` | "otpReference": {}, "userName": {}, "newPassword": {}, "tenantId": {}, "type": “Employee” |

#### **Stack**

1 → Language Selection Screen. + Login Screen + Forgot Password + Reset Password.

Pop → Forgot Password Screen.

Widgets Utilised from Library

| **SL No** | **Widgets** | **File Path** | **Description** |
| :--- | :--- | :--- | :--- |
| 1 | `BuildTextField` | [![](https://github.com/fluidicon.png)punjab-mgramseva/TextFieldBuilder.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/widgets/TextFieldBuilder.dart) | Text Field |
| 2 | `BottomButtonBar` | [![](https://github.com/fluidicon.png)punjab-mgramseva/BottonButtonBar.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/widgets/BottonButtonBar.dart) | Button |
| 3 | `PasswordHint` | [![](https://github.com/fluidicon.png)punjab-mgramseva/PasswordHint.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/widgets/PasswordHint.dart) | Password Hint Card |

