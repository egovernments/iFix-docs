# Adapter Services

## Overview

 Ifix-Adapter is a system that works as a mediator between iFix and its clients. This system will receive requests from the client system and convert the data in the Ifix required format. This document contains the details about how to set up ifix-adapter service and describes the functionalities it provides.

## Pre-requisites

Before you proceed with the configuration, make sure the following pre-requisites are met -

* _Java 8_
* Kafka server is up and running
* PSQL server is running
* Redis
* Following services should be up and running:
  * Client Service Like mgramseva-ifix-adapter
  * Target service IFIX- fiscal-event-service
  * Target Service IFIX-keycloak

## Key Functionalities

* Ifix client requests pushed to IFIX
* Auth token is fetched from keycloak and cached. Token will be re-fetched 5 minutes before expiry
* Every push to Ifix is recoded with HTTP status
  * status series 200 series considered a success
  * status 400 are marked client error and reported back to the client
  * status 500 resubmitted by the scheduler

## Deployment Details

1. update the keycloak credentials client-id and secrets in the environment file
2.  Map the COA in HeadCodeToCoaMapping.yml
3. Map project in ProjectMapping.yml
4. Deploy the latest version of ifix-reference-adapter

## Configuration Details

1. Update Key cloak credentials in dev.yaml,qa.yaml,prod.yaml according to environment

## Interaction Diagram

![](../../.gitbook/assets/image-20210906-060851.png)

Reference

[YAML Link](https://github.com/egovernments/iFix-Dev/blob/adaptor-dev/reference-adapter/iFix-adapter-v1.0.yaml)

