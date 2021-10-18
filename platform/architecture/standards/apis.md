# APIs

## Business Service

### Fiscal Service

{% swagger baseUrl="https://<<Host URL>>" path="/fiscal/events/v1/_push" method="post" summary="Post Fiscal Event" %}
{% swagger-description %}
Post fiscal events to the iFIX platform.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authentication" type="string" %}
Authentication token to track down who is emptying our stocks.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="requestHeader" type="object" %}
The API will do its best to find a cake matching the provided recipe.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="fiscalEvent" type="object" %}
Whether the cake should be gluten-free or not.
{% endswagger-parameter %}

{% swagger-response status="202" description="Fiscal Event Published Successfully" %}
```
{
  "responseHeader": {
    "ts": 0,
    "correlationId": "string",
    "msgId": "string",
    "status": "SUCCESS",
    "signature": "string",
    "version": "string"
  },
  "fiscalEvent": [
    {
      "id": "fecbbf1d-d6e3-4f24-9935-02c33b9248e0",
      "tenantId": "pb",
      "projectId": "090d1d25-8b88-46a3-b4c9-95b66483beb5",
      "eventType": "Appropriation",
      "eventTime": 1628177497000,
      "ingestionTime": 1628177497000,
      "referenceId": "013e9c56-8207-4dac-9f4d-f1e20bd824e7",
      "parentEventId": "7d476bb0-bc9f-48e2-8ad4-5a4a36220779",
      "parentReferenceId": "77f23efe-879d-407b-8f23-7b8dd5b2ecb1",
      "amountDetails": [
        {
          "id": "51c9c03c-1607-4dd5-9e0e-93bbf860f6f7",
          "amount": 10234.5,
          "coaId": "d1e87330-4de0-4d15-8d92-d40bfa9b3ca4",
          "fromBillingPeriod": 1622907239000,
          "toBillingPeriod": 1628177643000
        }
      ],
      "auditDetails": {
        "createdBy": "string",
        "lastModifiedBy": "string",
        "createdTime": 0,
        "lastModifiedTime": 0
      },
      "attributes": {}
    }
  ]
}
```
{% endswagger-response %}

{% swagger-response status="400" description="Failed to process request." %}
```
{
  "responseHeader": {
    "ts": 0,
    "correlationId": "string",
    "msgId": "string",
    "status": "SUCCESS",
    "signature": "string",
    "version": "string"
  },
  "errors": [
    {
      "code": "string",
      "message": "string",
      "description": "string"
    }
  ]
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger baseUrl="https://<<Host Url>>" path="/fiscal/events/v1/_search" method="get" summary="Search Fiscal Event" %}
{% swagger-description %}
Search fiscal events based on the provided search parameters
{% endswagger-description %}

{% swagger-parameter in="body" name="requestHeader" type="object" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="crietria" type="object" %}

{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
  "responseHeader": {
    "ts": 0,
    "correlationId": "string",
    "msgId": "string",
    "status": "SUCCESS",
    "signature": "string",
    "version": "string"
  },
  "fiscalEvent": [
    {
      "id": "fecbbf1d-d6e3-4f24-9935-02c33b9248e0",
      "tenantId": "pb",
      "projectId": "090d1d25-8b88-46a3-b4c9-95b66483beb5",
      "eventType": "Appropriation",
      "eventTime": 1628177497000,
      "ingestionTime": 1628177497000,
      "referenceId": "013e9c56-8207-4dac-9f4d-f1e20bd824e7",
      "parentEventId": "7d476bb0-bc9f-48e2-8ad4-5a4a36220779",
      "parentReferenceId": "77f23efe-879d-407b-8f23-7b8dd5b2ecb1",
      "amountDetails": [
        {
          "id": "51c9c03c-1607-4dd5-9e0e-93bbf860f6f7",
          "amount": 10234.5,
          "coaId": "d1e87330-4de0-4d15-8d92-d40bfa9b3ca4",
          "fromBillingPeriod": 1622907239000,
          "toBillingPeriod": 1628177643000
        }
      ],
      "auditDetails": {
        "createdBy": "string",
        "lastModifiedBy": "string",
        "createdTime": 0,
        "lastModifiedTime": 0
      },
      "attributes": {}
    }
  ]
}
```
{% endswagger-response %}

{% swagger-response status="400" description="Invalid Input" %}
```
{
  "ResponseHeader": {
    "ts": 0,
    "correlationId": "string",
    "msgId": "string",
    "status": "SUCCESS",
    "signature": "string",
    "version": "string"
  },
  "Errors": [
    {
      "code": "string",
      "message": "string",
      "description": "string"
    }
  ]
}
```
{% endswagger-response %}
{% endswagger %}
