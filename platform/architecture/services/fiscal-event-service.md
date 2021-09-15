# Fiscal Event Service

## Overview

It maintains the fiscal event flow activities of many projects. Root level entity is a tenant \(State Government\) under which we tag certain projects and all these entities information and COA \(Chart of Account\) passed along with amount details which makes a single fiscal event instance under the system.

## Version History

Current Version: 0.1.0

## Prerequisites

Before you proceed with the configuration, make sure the following pre-requisites are met.

1. Java 8
2. MongoDB instance
3. Required Service Dependencies.
   1. iFIX-Master-Data-Service
   2. iFIX-Department Entity Service
   3. iFIX-Fiscal Event Post Processor
   4. Apache Kafka Server

## Features

This service provides two features:

### Push fiscal event data

It is a secure endpoint and user Info details are required to access it  
It receives fiscal detail along with mandatory tenant and project info in push request, that triggers the whole fiscal event process and forward it to post-process service.  
Before encompassing all entities, it checks for entities validation via Master Data Service.  
While we create any fiscal event instance in the system, we log ingestion time and event occurrence timestamp which makes event flow more clear on timestamp activities.  
After processing all these activities, it passes fiscal event information to other fiscal event post-processor services for further processing by publishing fiscal data into the kafka topic "fiscal-event-request-validated".  
It also responds to snapshot of enriched fiscal event data which can be used by the source system for reference or any further processing.

### Search fiscal Event Data

It provides a search feature on the existing fiscal event which has been processed before by post-processor service and persisted into the MongoDB instance.  
We can mainly search on eventType, tenantId and event time interval and in return we get enriched data \(dereference with nested id details\).

Fiscal Event Service enables iFIX clients to post and search fiscal events. 

![](../../../.gitbook/assets/image%20%286%29.png)



## Configurations and Setup

1. Update all the DB and URI configuration in the dev.yaml, qa.yaml, prod.yaml file.
2. Make sure keycloak server is up and running And have been configured with the required client ID.

References

1. [Swagger YAML ](https://redocly.github.io/redoc/?url=https://raw.githubusercontent.com/egovernments/iFix-Dev/develop/domain-services/fiscal-event-service/fiscal-event-service-0.1.0.yaml)

