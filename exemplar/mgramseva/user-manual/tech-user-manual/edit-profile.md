# Edit Profile

## **Link**

→ {base url}/mgramseva/home/editProfile

![](../../../../.gitbook/assets/image%20%2875%29.png)

Users are navigated to this screen if they click on the Edit Profile option on the Side Bar app Drawer.![](blob:https://digit-discuss.atlassian.net/6fab3b7c-764f-4cd5-ad69-248197e2873e#media-blob-url=true&id=2cba3990-808e-45ec-8e26-0681e2361567&collection=contentId-1925709827&contextId=1925709827&mimeType=image%2Fpng&name=EditProfile.png&size=28631&width=377&height=818&alt=)

## **User Interaction on Screen**

* User can change their profile name, gender and email on this screen
* Click on the Save button triggers a Details Saved Successfully message on the screen and saves the changes to the profile.

## **File Path**

Primary Files:[ ![](https://github.com/fluidicon.png)punjab-mgramseva/EditProfile.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/screeens/Profile/EditProfile.dart)

## **Field Validations**

| **SL** | **Fileds** | **Validations** |
| :--- | :--- | :--- |
| 1 | Name | `r'^[a-zA-Z ]+$'` |
| 2 | Email ID | `r'^$|^(([^<>()[\]\\.,;:\s@\"]+(\.[^<>()[\]\\.,;:\s@\"]+)*)|(\".+\"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$'` |

## **API Details**

| **SL** | **End Point** | **Request Method** | **Request Info** |
| :--- | :--- | :--- | :--- |
| 1 | `/user/profile/_update` | `POST` | "user": { "id": {}, "userName": {}, "salutation": null, "name": {}, "gender": {}, "mobileNumber": "9191919146", "emailId": {}, "altContactNumber": null, "pan": null, "aadhaarNumber": null, "permanentAddress": null, "permanentCity": null, "permanentPinCode": null, "correspondenceAddress": null, "correspondenceCity": null, "correspondencePinCode": null, "active": true, "locale": null, "type": "EMPLOYEE", "accountLocked": false, "accountLockedDate": 0, "fatherOrHusbandName": null, "relationship": null, "signature": null, "bloodGroup": null, "photo": null, "identificationMark": null, "createdBy": {}, "lastModifiedBy": {}, "tenantId": {}, "roles": \[ {} \], } |

### **Stack**

1 → Home Screen. + Edit Profile Screen

Pop → Home Screen

Widgets Utilised from Library

| **SL No** | **Widgets** | **File Path** | **Description** |
| :--- | :--- | :--- | :--- |
| 1 | `BuildTextField` | [![](https://github.com/fluidicon.png)punjab-mgramseva/TextFieldBuilder.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/widgets/TextFieldBuilder.dart) | Text Field |
| 2 | `BottomButtonBar` | [![](https://github.com/fluidicon.png)punjab-mgramseva/BottonButtonBar.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/widgets/BottonButtonBar.dart) | Button |
| 3 | `RadioButtonField` | [![](https://github.com/fluidicon.png)punjab-mgramseva/RadioButtonFieldBuilder.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/widgets/RadioButtonFieldBuilder.dart) | Radio Buttons for options |



