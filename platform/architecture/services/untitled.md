# Fiscal Event Post Processor

## Overview

Fiscal Event Post Processor is a streaming pipeline for validated fiscal event data. Apache Kafka has been used to stream the validated fiscal event data, process it for dereference, unbundle, flatten And finally push these details to Mongo and Druid data store.

## Version History

Current version : 0.1.0

## Prerequisites

Before you proceed with the configuration, make sure the following pre-requisites are met

1. Java 8
2. Apache Kafka and Kafka-Connect server should be up and running.
3. Druid DB & MongoDB should be up and running.
4. Below dependent services are required :  iFix Master data service.  iFix Fiscal Event service.

## Features

Fiscal Event post processor consumes the fiscal event validated data from Kafka topic named “fiscal-event-request-validated” and process it by following below steps :

1. Fiscal event validated data will get dereferenced. For dereferencing , pass the service ids like project id, COA id, Tenant id etc. to corresponding services - Master service & Department Entity service And get the corresponding object\(s\). Once the fiscal event data is dereferenced, push/send the same data to Mongo Sink and dereference Topic.
2. Mongo connector will pick up the data from “fiscal-event-mongodb-sink“ topic and push it to Mongo Datastore.
3. Unbundle consumers will pick up the dereferenced fiscal event data from dereferenced topic. Dereference fiscal event data will get unbundled and then flattened. Once the flattening is complete, push/send the same data to Druid Sink topic.
4. Flattened fiscal event data will be pushed to Druid DB from topic named: fiscal-event-druid-sink.

## Kafka to Data Store Sink

### MongoDB Sink

We can use Kafka-connect to push the data from a Kafka topic to MongoDB. We will have to follow these steps to start the connector:

1. Connect\(port-forward\) with the Kafka-connect server.
2. We can create a new connector with a POST API call to localhost:8083/connectors.
3. The request body for that API call is written in the below JSON file :

```text
{
  "name": "fiscal-event-mongodb-sink",
  "config": {
    "connector.class": "com.mongodb.kafka.connect.MongoSinkConnector",
    "connection.uri": "${mongo-db-authenticated-uri}",

    "database": "${mongo-db-name}",
    "collection": "fiscal_event",

    "topics": "fiscal-event-mongodb-sink",

    "key.ignore": "true",
    "schema.ignore": true,
    "value.converter.schemas.enable": false,
    "key.converter": "org.apache.kafka.connect.storage.StringConverter",
    "value.converter": "org.apache.kafka.connect.json.JsonConverter",

    "mongo.errors.tolerance": "all",
    "mongo.errors.log.enable": true,
    "errors.log.enable": true,
    "errors.deadletterqueue.context.headers.enable": true,
    "errors.deadletterqueue.topic.name": "fiscal-event-mongodb-dead-letter",

    "batch.size": 500,
    "max.buffered.records": 1000,
    "flush.timeout.ms": 600000,
    "retry.backoff.ms": 5000,
    "read.timout.ms": 10000,
    "linger.ms": 1000,
    "max.in.flight.requests": 2,

    "tasks.max": 1
  }
}
```

4. Within that file, wherever ${---} replace it with the actual value based on the environment. Get ${mongo-db-authenticated-uri} from the configured secrets of the environment.  
\(Optional\) Verify and make changes to the topic names.

5. The connector is ready. You can check it using API call GET localhost:8083/connectors.

### Druid Sink

We will use the Druid console to start ingesting data from a Kafka topic to the Druid data store. Please follow the steps mentioned below to start the Druid Supervisor

* Open the Druid console
* Go to the Load Data section
* Select Other
* Click on Submit Supervisor
* Copy...Paste the JSON from the below file in the available text box.

```text
{
  "type": "kafka",
  "spec": {
    "ioConfig": {
      "type": "kafka",
      "consumerProperties": {
        "bootstrap.servers": "kafka-v2.ifix:9092"
      },
      "topic": "fiscal-event-druid-sink",
      "inputFormat": {
        "type": "json"
      },
      "useEarliestOffset": true
    },
    "tuningConfig": {
      "type": "kafka"
    },
    "dataSchema": {
      "dataSource": "fiscal-event",
      "timestampSpec": {
        "column": "eventTime",
        "format": "millis"
      },
      "transformSpec": {
        "transforms": [
          {
            "type": "expression",
            "name": "bill",
            "expression": "if(\"eventType\" == 'BILL', \"amount\", 0)"
          },
          {
            "type": "expression",
            "name": "receipt",
            "expression": "if(\"eventType\" == 'RECEIPT', \"amount\", 0)"
          },
          {
            "type": "expression",
            "name": "payment",
            "expression": "if(\"eventType\" == 'PAYMENT', \"amount\", 0)"
          },
          {
            "type": "expression",
            "name": "demand",
            "expression": "if(\"eventType\" == 'DEMAND', \"amount\", 0)"
          }
        ]
      },
      "dimensionsSpec": {
        "dimensions": [
          "id",
          {
            "type": "double",
            "name": "amount"
          },

          "version",
          "tenantId",
          "eventId",
          {
            "type": "long",
            "name": "ingestionTime"
          },
          "eventType",
          "referenceId",
          "parentEventId",
          "parentReferenceId",

          {
            "type": "long",
            "name": "fromBillingPeriod"
          },
          {
            "type": "long",
            "name": "toBillingPeriod"
          },

          "coa.id",
          "coa.coaCode",
          "coa.majorHead",
          "coa.majorHeadName",
          "coa.subMajorHead",
          "coa.subMajorHeadName",
          "coa.minorHead",
          "coa.minorHeadName",
          "coa.subHead",
          "coa.subHeadName",
          "coa.groupHead",
          "coa.groupHeadName",
          "coa.objectHead",
          "coa.objectHeadName",

          "department.id",
          "department.code",
          "department.name",

          "departmentEntity.id",
          "departmentEntity.code",
          "departmentEntity.name",
          "departmentEntity.hierarchyLevel",

          "departmentEntity.ancestry[0].id",
          "departmentEntity.ancestry[0].code",
          "departmentEntity.ancestry[0].name",
          "departmentEntity.ancestry[0].hierarchyLevel",
          "departmentEntity.ancestry[1].id",
          "departmentEntity.ancestry[1].code",
          "departmentEntity.ancestry[1].name",
          "departmentEntity.ancestry[1].hierarchyLevel",
          "departmentEntity.ancestry[2].id",
          "departmentEntity.ancestry[2].code",
          "departmentEntity.ancestry[2].name",
          "departmentEntity.ancestry[2].hierarchyLevel",
          "departmentEntity.ancestry[3].id",
          "departmentEntity.ancestry[3].code",
          "departmentEntity.ancestry[3].name",
          "departmentEntity.ancestry[3].hierarchyLevel",
          "departmentEntity.ancestry[4].id",
          "departmentEntity.ancestry[4].code",
          "departmentEntity.ancestry[4].name",
          "departmentEntity.ancestry[4].hierarchyLevel",
          "departmentEntity.ancestry[5].id",
          "departmentEntity.ancestry[5].code",
          "departmentEntity.ancestry[5].name",
          "departmentEntity.ancestry[5].hierarchyLevel",
          "departmentEntity.ancestry[6].id",
          "departmentEntity.ancestry[6].code",
          "departmentEntity.ancestry[6].name",
          "departmentEntity.ancestry[6].hierarchyLevel",
          "departmentEntity.ancestry[7].id",
          "departmentEntity.ancestry[7].code",
          "departmentEntity.ancestry[7].name",
          "departmentEntity.ancestry[7].hierarchyLevel",
          "departmentEntity.ancestry[8].id",
          "departmentEntity.ancestry[8].code",
          "departmentEntity.ancestry[8].name",
          "departmentEntity.ancestry[8].hierarchyLevel",
          "departmentEntity.ancestry[9].id",
          "departmentEntity.ancestry[9].code",
          "departmentEntity.ancestry[9].name",
          "departmentEntity.ancestry[9].hierarchyLevel",
          "departmentEntity.ancestry[10].id",
          "departmentEntity.ancestry[10].code",
          "departmentEntity.ancestry[10].name",
          "departmentEntity.ancestry[10].hierarchyLevel",

          "expenditure.id",
          "expenditure.code",
          "expenditure.name",
          "expenditure.type",

          "government.id",
          "government.name",

          "project.id",
          "project.code",
          "project.name",

          {
            "name": "bill",
            "type": "double"
          },
          {
            "name": "receipt",
            "type": "double"
          },
          {
            "name": "demand",
            "type": "double"
          },
          {
            "name": "payment",
            "type": "double"
          }
        ]
      },
      "granularitySpec": {
        "queryGranularity": "none",
        "rollup": false,
        "segmentGranularity": "hour"
      }
    }
  }
}
```

* You should verify the Kafka topic name and the Kafka bootstrap server address before submitting the config.
* Now submit the config and the data ingestion should start into the fiscal-event data source.

## Interaction Diagram

![](../../../.gitbook/assets/fiscal-event-processing-piepline.png)

## Configurations and Setup

Update all the DB, Kafka producer & Consumer And URI configuration in the dev.yaml, qa.yaml, prod.yaml file.

Reference 

[Swagger.YAML](https://github.com/egovernments/iFix-Dev/blob/develop/domain-services/fiscal-event-post-processor/fiscal-event-post-processor-0.1.0.yaml)

