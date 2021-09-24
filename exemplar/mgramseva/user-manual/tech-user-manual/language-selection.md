# Language Selection

## **Link**

→ {base url}/mgramseva/selectLanguage

User will be Landed/ Navigated to Language Selection Screen

![](../../../../.gitbook/assets/image%20%2886%29.png)

APP → Initial Screen

### **User Interaction on Screen**

* Users can switch to different languages which the application supports
* Click on [Continue](https://digit-discuss.atlassian.net/wiki/spaces/DD/pages/1922269219) to navigate to the next screen

### **File Path**

Primary Files[ ![](https://github.com/fluidicon.png)punjab-mgramseva/languageSelection.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/screeens/SelectLanguage/languageSelection.dart)

Secondary Files[ ![](https://github.com/fluidicon.png)punjab-mgramseva/DesktopView.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/screeens/SelectLanguage/DesktopView.dart)[ ![](https://github.com/fluidicon.png)punjab-mgramseva/MobileView.dart at develop · egovernments/punjab-mgramseva](https://github.com/egovernments/punjab-mgramseva/blob/develop/frontend/mgramseva/lib/screeens/SelectLanguage/MobileView.dart)

### **Data Storage** 

LocalStorage

| **SL No** | **Key** | **Stored Data** |
| :--- | :--- | :--- |
| 1 | `states_key` | State Information for From MDMS Service |
| 2. | ex :`pn_IN`,`en_IN`,`hi_IN` | Localisation codes |

## **API Details**

<table>
  <thead>
    <tr>
      <th style="text-align:left"><b>API EndPoint</b>
      </th>
      <th style="text-align:left"><b>Input Params (Modules)</b>
      </th>
      <th style="text-align:left"><b>Description</b>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><code>egov-mdms-service/v1/_search</code>
      </td>
      <td style="text-align:left">
        <p><code>common-masters</code>
        </p>
        <p><code>tenant</code>
        </p>
      </td>
      <td style="text-align:left">
        <p>To Fetch the Details</p>
        <p><b>State Info</b>
        </p>
        <ul>
          <li>Logo</li>
          <li>background Image</li>
          <li>Languages Supported</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>localization/messages/v1/_search?module</code>={}<code>locale</code>={}<code>tenantId</code>={}</td>
      <td
      style="text-align:left">ALL the necessary Modules, with locale key and tenant Id</td>
        <td style="text-align:left">To Load the Localised data</td>
    </tr>
  </tbody>
</table>

### **Stack**

0 → Langage Selection Screen

Pop → Application closes

Widgets Utilised from Library

| **SL No** | **Widgets Library** |
| :--- | :--- |
| 1 | Button Bar |

