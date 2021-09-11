---
description: Work in Progress
---

# Architecture

mGramSeva is built on top of the [Digit ](https://docs.digit.org/)Platform. It consists of the following layers

1. Front End
2. Back End
   1. Core Services
      1. [User Service](https://docs.digit.org/configuration/configure-digit/services-overview/core-services/user-services) \(egov-user\)
      2. User OTP \(user-otp\)
      3. [Access Control](https://docs.digit.org/configuration/configure-digit/services-overview/core-services/access-control-services) \(access-control\)
      4. [MDMS](https://docs.digit.org/configuration/configure-digit/services-overview/core-services/mdms-services)
      5. [ID Generation Service](https://digit-discuss.atlassian.net/wiki/spaces/EPE/pages/37060616/ID-Generation-Service) \(id-gen\)
      6. [Payment Gateway](https://docs.digit.org/configuration/configure-digit/services-overview/core-services/payment-gateway-services) \(pg-service\)
      7. [Workflow Service ](https://docs.digit.org/configuration/configure-digit/services-overview/core-services/workflow-services)\(wf-service\)
      8. [Persister](https://digit-discuss.atlassian.net/wiki/spaces/EPE/pages/37322761/Persister-Service)
      9. [Indexer](https://docs.digit.org/configuration/configure-digit/services-overview/core-services/indexer-service)
      10. [Encryption Service ](https://digit-discuss.atlassian.net/wiki/spaces/EPE/pages/5832708/Encryption+Service)\(data-encryption-service\)
      11. [Localization Service ](https://digit-discuss.atlassian.net/wiki/spaces/EPE/pages/336920792/eGov-Localisation)\(localization-service\)
      12. [Boundary Service](https://docs.digit.org/configuration/configure-digit/services-overview/core-services/location-services) \(location-service\)
      13. [URL Shortening Service](https://docs.digit.org/configuration/configure-digit/services-overview/core-services/url-shortening-service) \(url-shortening-service\)
      14. [PDG Generation Service](https://docs.digit.org/configuration/configure-digit/services-overview/core-services/pdf-generation-services) \(pdf-generator\)
      15. otp-service
      16. [SMS Notifications](https://digit-discuss.atlassian.net/wiki/spaces/EPE/pages/224919569/egov-notification-sms) \(notification-sms\)
      17. notification-email
      18. [Filestore](https://digit-discuss.atlassian.net/wiki/spaces/EPE/pages/37060620/File-Store-Service)
      19. [API Gateway](https://digit-discuss.atlassian.net/wiki/spaces/EPE/pages/36700192/API-Gateway)
   2. Business Services
      1. [Billing Service](https://docs.digit.org/configuration/configure-digit/services-overview/business-services/billing-service)
      2. [Collection service](https://docs.digit.org/configuration/configure-digit/services-overview/business-services/collection-service/collection-service-v2)
      3. [Apportioning Service](https://docs.digit.org/configuration/configure-digit/services-overview/business-services/appropriation-service)
      4. [Dashboard Ingest](https://docs.digit.org/configuration/configure-digit/services-overview/business-services/dss-technical-documentation)
      5. [Dashboard Analytics](https://docs.digit.org/configuration/configure-digit/services-overview/business-services/dashboard-analytics-backend) \(DSS\)
   3. Municipal services:
      1. [Property Service ](https://docs.digit.org/product/modules/property-tax/property-tax-service)\(property-services\)
      2. [Water Service Calculator](https://docs.digit.org/product/modules/water-and-sewerage/water-services/water-calculator-service) \(ws-calculator\)
      3. [Water Service](https://docs.digit.org/product/modules/water-and-sewerage/water-services) \(ws-service\)
      4. [eChallan](https://docs.digit.org/product/modules/e-challan-service) \(echallan\)
      5. [eChallan Calculator](https://docs.digit.org/product/modules/e-challan-service/echallan-calculator-services) \(echallan-calculator\)
      6. [User Events](https://digit-discuss.atlassian.net/wiki/spaces/EPE/pages/231407688/egov-user-events) \(user-event\)
      7. [Vendor](https://docs.digit.org/product/modules/faecal-sludge-management-fsm/fsm-service-configuration/fsm-vendor-registry-v1.0)

## Information Model

## Services Architecture

Each service is built as a microservices

## Technology 

## Deployment 

## Security 



