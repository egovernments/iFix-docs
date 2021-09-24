# iFix Fiscal Event Service

## Overview

It maintains the fiscal event flow activities of many projects. Root level entity is a tenant \(State Government\) under which we tag certain projects. All the entity information and COA \(Chart of Account\) are passed along with amount details which constitutes a single fiscal event instance under the system.

## Version History

Current Version: 1.0.0

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

* It is a secure endpoint and user Info details are required to access it.
* It receives fiscal detail along with mandatory tenant and project info in push requests, which triggers the whole fiscal event process and forwards it to the post-process service.
* Before encompassing all entities, it checks for entities validation via Master Data Service.
* While we create any fiscal event instance in the system, we log ingestion time and event occurrence timestamp which makes event flow more clear on timestamp activities.
* After processing all these activities, it passes fiscal event information to other fiscal event post-processor services for further processing by publishing fiscal data into the Kafka topic "fiscal-event-request-validated".
* It also responds to snapshot of enriched fiscal event data which can be used by the source system for reference or any further processing.

### Search fiscal Event Data

* It provides a search feature on the existing fiscal events which has been processed before by post-processor service and persisted into the MongoDB instance.
* We can mainly search on eventType, tenantId and event time interval and in return we get enriched data \(dereference with nested id details\).

## API List

|  | **Link** |
| :--- | :--- |
|  `/events/v1/_push` | [https://www.getpostman.com/collections/e9a94f8e896d8cfaa813](https://www.getpostman.com/collections/e9a94f8e896d8cfaa813) |
|  `/events/v1/_search` | [https://www.getpostman.com/collections/e9a94f8e896d8cfaa813](https://www.getpostman.com/collections/e9a94f8e896d8cfaa813) |

## Interaction Diagram

![](../../../.gitbook/assets/image%20%2865%29.png)

## Environment

_**Note:**_ _Kafka topic needs to be configured with respect to the environment_

| **Key** | **Value** | **Description** |
| :--- | :--- | :--- |
| fiscal-kafka-push-topic | fiscal-event-request-validated | Once the fiscal event data gets validated and enriched, it will be published on this topic for further processing |

## Configurations and Setup

1. Update all the DB and URI configuration in the dev.yaml, qa.yaml, prod.yaml file.
2. Make sure the keycloak server is up and running And have been configured with the required client ID.

## References and Notes

| **Title** | **Link** |
| :--- | :--- |
| Swagger Yaml | [ReDoc Interactive Demo](https://redocly.github.io/redoc/?url=https://raw.githubusercontent.com/egovernments/iFix-Dev/develop/domain-services/fiscal-event-service/fiscal-event-service-1.0.0.yaml) |
| Postman collection | [https://www.getpostman.com/collections/e9a94f8e896d8cfaa813](https://www.getpostman.com/collections/e9a94f8e896d8cfaa813) |

