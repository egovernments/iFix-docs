# Information Model

Government

| Field | Type | Description |
| :--- | :--- | :--- |
| id | String | Unique Identifier |
| name | String | Name of the Government or Tenant - e.g. India, Nigeria, Punjab |

Department

| Field | Type | Description |
| :--- | :--- | :--- |
| id | String | Unique Identifier |
| name | String | Name of the Department - e.g. Department of Water Supply and Sanitation |
| code | String | Unique Code e.g. DWSS |

Chart of Account

| Field | Type | Description |
| :--- | :--- | :--- |
| name | String | Name of the Account  |
| coaCode | String  | Full Chart of Account String eg: 1234-123-123-12-12-12 |
| majorHead | String | Major head code |
| majorHeadName | String | Major head name |
| majorHeadType | String | Major head code type |
| subMajorHead | String | Sub-Major head code |
| subMajorHeadName | String | Sub-Major head name |
| minorHead | String | Minor head code |
| minorHeadName | String | Minor head name |
| subHead | String | Sub-Head code |
| subHeadName | String | Sub-Head name |
| groupHead | String | Group head code |
| groupHeadName | String | Group head name |
| objectHead | String | Object head code |
| objectHeadName | String | Object head name |

Expenditure - encapsulates all scheme and non-scheme expenditure.

| Field | Type | Description |
| :--- | :--- | :--- |
| id | String | Unique Identifier |
| name | String | Name of the Expenditure - This could be a scheme or a non-scheme expenditure - e.g. Jal Jeevan Mission |
| code | String | Unique Code e.g. JJM |
| type | Enum | Type of Expenditure - \[Scheme, Non-Scheme\] |

Project

| Field | Type | Description |
| :--- | :--- | :--- |
| id | String | Unique Identifier |
| name | String | Name of the Project - e.g. Kartarpur Sahib Water Supply Project |

Amount

| Field | Type | Description |
| :--- | :--- | :--- |
| id | String | Unique Identifier |
| amount | Number | Transaction Amount |
| coaId | String | Chart of Account ID |
| fromBillingPeriod | Integer\($int64\) | Start date of the billing period for which transaction is applicable |
| toBillingPeriod | Integer\($int64\) | End date of the billing period for which transaction is applicable |

Fiscal Event

| Field | Type | Description |
| :--- | :--- | :--- |
| version | String | Version of the Information Model |
| id | String | System Generated Unique ID |
| tenantId | String | Government ID |
| projectId | String | Unique ID of the Associated Project  |
| eventType | String | Type of Fiscal Event e.g. Demand, Bill, Payment, Receipt |
| eventTime | integer\($int64\) | Time Stamp when the event occurred in the source system |
| referenceId | String | Unique Transaction Reference ID in the source system |
| parentEventId | String | Unique ID of the Parent Event to which this event is linked |
| amountDetails | Array\[Amount\] | Array of type Amount |
|  |  |  |

