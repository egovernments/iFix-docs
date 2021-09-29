# Fiscal Event Aggregator

## Overview

Fiscal Event Aggregator is a java standalone application, which runs as Cron Job to aggregate the fiscal event data from the Druid data store to Postgres DB.

## Version History

Current Version : 1.0.0

## Prerequisites

Before you proceed with the configuration, make sure the following pre-requisites are met

1. Java 8
2. Druid DB & Postgres DB should be up and running

## Features

The fiscal event aggregator gets the fiscal event data from Druid DB based on fiscal periods and configured department hierarchy level. Currently, it pulls the fiscal event data by hardcoded fiscal period and is supported at the department hierarchy level in Druid DB. 

Below steps are there to aggregate the fiscal event data :

1. Group the sum of amount based on project id, COA\(chart of account\) id, and event type.
2. Difference of sum of the amount of "DEMAND" and "RECEIPT" event type with respect to distinct project id.
3. Difference of sum of the amount of "BILL" and "PAYMENT" event type with respect to distinct project id.

Upsert the final aggregated fiscal event data into the Postgres DB.

## Environment

_Note: Below environment variables need to be configured with respect to the environment_

| **Key** | **Value** | **Description** |
| :--- | :--- | :--- |
| `DRUID_CONNECT_PROTOCOL` | `HTTP` | This is a hardcoded value And won’t change w.r.t environment. And It depends upon the druid broker’s protocol that is getting used to connect. |
| `DRUID_CONNECT_PORT` | `8082` | This is a hardcoded value And won’t change w.r.t environment. It depends upon the druid broker protocol that we are using and the corresponding port of that druid broker protocol. |
| `DRUID_HOST` | `druid-broker.olap` | this is kept under `configmaps`. |
| `FISCAL_EVENT_DATASOURCE` | `fiscal-event` | This is the data Source present in Druid DB. It will same as defined in Druid DB. |

## Interaction Diagram

![](../../../.gitbook/assets/image%20%2899%29.png)

## Configuration

Update all the configuration in the dev.yaml, qa.yml, prod.yaml file.

