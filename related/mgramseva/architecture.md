---
description: Work in Progress
---

# Architecture

mGramSeva is built on top of the [Digit ](https://docs.digit.org/)Platform. It consists of the following layers

1. Front End
2. Back End
   1. Core Services
      1. [User Service](https://digit-discuss.atlassian.net/wiki/spaces/DD/pages/669450371/User+Service) \(egov-user\)
      2. User OTP \(user-otp\)
      3. [Access Control](https://digit-discuss.atlassian.net/wiki/spaces/DD/pages/695664711/Access+Control+Service) \(access-control\)
      4. [MDMS](https://digit-discuss.atlassian.net/wiki/spaces/DD/pages/723189807/MDMS+Master+Data+Management+Service)
      5. [ID Generation Service](https://digit-discuss.atlassian.net/wiki/spaces/EPE/pages/37060616/ID-Generation-Service) \(id-gen\)
      6. pg-service
      7. [Workflow Service ](https://digit-discuss.atlassian.net/wiki/spaces/EPE/pages/37093389/Workflow-Service)\(wf-service\)
      8. [Persister](https://digit-discuss.atlassian.net/wiki/spaces/EPE/pages/37322761/Persister-Service)
      9. [Indexer](https://digit-discuss.atlassian.net/wiki/spaces/DD/pages/888963174/Indexer+Service)
      10. [Encryption Service ](https://digit-discuss.atlassian.net/wiki/spaces/EPE/pages/5832708/Encryption+Service)\(data-encryption-service\)
      11. [Localisation Service ](https://digit-discuss.atlassian.net/wiki/spaces/EPE/pages/336920792/eGov-Localisation)\(localization-service\)
      12. Boundary-service
      13. [URL Shortening Service](https://digit-discuss.atlassian.net/wiki/spaces/DD/pages/896892936/URL+Shortening+service) \(url-shortening-service\)
      14. [PDG Generation Service](https://digit-discuss.atlassian.net/wiki/spaces/DD/pages/717979679/PDF+Generation+Service) \(pdf-generator\)
      15. otp-service
      16. notification-sms
      17. notification-email
      18. filestore
      19. [API Gateway](https://digit-discuss.atlassian.net/wiki/spaces/EPE/pages/36700192/API-Gateway)
   2. Business Services
      1. [Billing Service](https://digit-discuss.atlassian.net/wiki/spaces/DD/pages/1620672528/Billing+Service)
      2. [Collection service](https://digit-discuss.atlassian.net/wiki/spaces/DD/pages/1620574288/Collection+Service+V2)
      3. Apportioning-service
      4. Dashboard-ingest
      5. Dashboard-Analytics
   3. Municipal services:
      1. [Property Service ](https://digit-discuss.atlassian.net/wiki/spaces/DD/pages/1620181050/Property+Services)\(property-services\)
      2. [Water Service Calculator](https://digit-discuss.atlassian.net/wiki/spaces/DD/pages/1652654175/Water+Calculator+Service) \(ws-calculator\)
      3. [Water Service](https://digit-discuss.atlassian.net/wiki/spaces/DD/pages/1652359171/Water+Service) \(ws-service\)
      4. [eChallan](https://digit-discuss.atlassian.net/wiki/spaces/DD/pages/1531740173/eChallans+Service) \(echallan\)
      5. [eChallan Calculator](https://digit-discuss.atlassian.net/wiki/spaces/DD/pages/1561034755/eChallan+Calculator+Services) \(echallan-calculator\)
      6. user-event
      7. vendor

## Information Model

## Services Architecture

Each service is built as a microservices

## Technology 

## Deployment 

## Security 



