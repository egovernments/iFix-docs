# APIs

## Business Service

### Fiscal Service

{% api-method method="post" host="https://<<Host URL>>" path="/fiscal/events/v1/\_push" %}
{% api-method-summary %}
Post Fiscal Event
{% endapi-method-summary %}

{% api-method-description %}
Post fiscal events to the iFIX platform.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
Authentication token to track down who is emptying our stocks.
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="requestHeader" type="object" required=true %}
The API will do its best to find a cake matching the provided recipe.
{% endapi-method-parameter %}

{% api-method-parameter name="fiscalEvent" type="object" required=true %}
Whether the cake should be gluten-free or not.
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=202 %}
{% api-method-response-example-description %}
Fiscal Event Published Successfully
{% endapi-method-response-example-description %}

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
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
Failed to process request.
{% endapi-method-response-example-description %}

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
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://<<Host Url>>" path="/fiscal/events/v1/\_search" %}
{% api-method-summary %}
Search Fiscal Event
{% endapi-method-summary %}

{% api-method-description %}
Search fiscal events based on the provided search parameters
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-form-data-parameters %}
{% api-method-parameter name="requestHeader" type="object" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="crietria" type="object" required=true %}

{% endapi-method-parameter %}
{% endapi-method-form-data-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

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
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
Invalid Input
{% endapi-method-response-example-description %}

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
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

