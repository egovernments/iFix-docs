# iFix Department Entity Service

## Overview

Department Entity service manages the department and its hierarchies metadata. It deals with department entity and department hierarchy only.  
Department Hierarchy store only hierarchies definition like metadata for department level and department entity stores actual department data with its ancestry information.

## Version History

Current Version: 1.0.0

## Prerequisites

Before you proceed with the configuration, make sure the following pre-requisites are met.

1. Java 8
2. MongoDB instance
3. Required Service Dependencies - iFIX-Master-Data-Service 

## Features

### Department Hierarchy

It defines the hierarchy definition for the department.

* department id: It is the ID of the department from the department master
* level: It defines the depth of hierarchy of department-level
* parent: It provides details about department hierarchy parent \(UUID\)

#### **Level Value Evaluation**

1. Root level department hierarchy will not contain any parent value and level value will be zero
2. When parent id is having any value then we search parent in department hierarchy record for hierarchy level evaluation
3. Get level value from parent department hierarchy and increment current department hierarchy level value by one

### Department Entity

It contains department entity information along with its hierarchy level and also attaches master department information \(department id - UUID\). It keeps all child level information lists at every department node \(department record\). Leaf level department does not have any children info.  
Child list contains department entity ID list, which makes current department entity parent of all children list \(department ID list\). This is how it maintains the department entity level.

#### Hierarchy Level Approach

Define the hierarchy level using the top to bottom because it has the parent's references. For department entity, create using the bottom-to-top approach. The leaf department entity does not have any child reference. When the department entity goes higher \(parent\) only then it defines child reference in its child list.

### Department Hierarchy Request Action

1. **Create Department Hierarchy:** We pass the current hierarchy level and its parent details along with master department and tenant information. It stores data as meta-information about hierarchy level for department entity data processing, it works as a reference meta index which will tell about hierarchy level information.
2. **Search Department Hierarchy:** It just provides a preview of department hierarchies by providing request parameters - tenant Id, hierarchy level or department hierarchy id.

#### **API List**

|  | **Link** |
| :--- | :--- |
|  `/departmentEntity/hierarchyLevel/v1/_create` | [https://www.getpostman.com/collections/b330dc3698bf009d2ef5](https://www.getpostman.com/collections/b330dc3698bf009d2ef5) |
|  `/departmentEntity/hierarchyLevel/v1/_search` | [https://www.getpostman.com/collections/b330dc3698bf009d2ef5](https://www.getpostman.com/collections/b330dc3698bf009d2ef5) |

### Department Entity Request Action

1. **Create Department Entity:** It passes tenant Id, master department id, hierarchy level, its children list with department entity name and code. Tenant, hierarchy level and the master department is root info about the department entity. If the department entity does not contain any child, that means it is a leaf department entity it can only seek for its parent.
2. **Search Department Entity:** It can make search requests based on any department entity attribute but can't skip tenant information, it returns the whole department entity details along with its child information. It finds all ancestry information of the current department entity.

#### **API List**

|  | **Link** |
| :--- | :--- |
|  `/departmentEntity/v1/_create` | [https://www.getpostman.com/collections/b330dc3698bf009d2ef5](https://www.getpostman.com/collections/b330dc3698bf009d2ef5) |
|  `/departmentEntity/v1/_search` | [https://www.getpostman.com/collections/b330dc3698bf009d2ef5](https://www.getpostman.com/collections/b330dc3698bf009d2ef5) |

## Interaction Diagram

![](../../../.gitbook/assets/image%20%2861%29.png)

## Environment

There will not be any environment variables required specific to the environment \(migration\).

## Configurations and Setup

1. Update all the DB and URI configuration in the dev.yaml, qa.yaml, prod.yaml file.
2. Make sure the Keycloak server is up and running And have been configured with the required client ID.

## References and Notes

| **Title** | **Link** |
| :--- | :--- |
| Swagger Yaml | [ReDoc Interactive Demo](https://redocly.github.io/redoc/?url=https://raw.githubusercontent.com/egovernments/iFix-Dev/develop/domain-services/ifix-department-entity-service/ifix-department-entity-service-1.0.0.yaml) |
| Postman collection | [https://www.getpostman.com/collections/b330dc3698bf009d2ef5](https://www.getpostman.com/collections/b330dc3698bf009d2ef5) |

