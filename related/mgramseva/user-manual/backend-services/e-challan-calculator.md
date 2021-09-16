# e-Challan Calculator

### Overview <a id="Overview"></a>

eChallan Calculator service is used to calculate the echallan amount based on the details present in echallan request. This module is designed in such a way that it can be used to serve echallan for different types of service.

## Pre-requisites

Before you proceed with the configuration, make sure the following pre-requisites are met -

* _Java 8_
* Kafka server is up and running.
* PSQL server is running and a database is created to store eChallan Calculator Application data.
* Following services should be up and running:
  * egov-mdms
  * echallan-services
  * billing-service

## Key Functionalities

* echallan service internally call echallan-calculator to generate a demand.
* Based on the taxhead and tax amount defined in echallan request, echallan calculator service creates the demand.
* After Demand creation, it calls the billing service to generate the fees.

## Configuration Details

**MDMS Config**

Define the tax period in the below mdms file for the business service which are allowed in echallan service.[ ![](https://github.com/fluidicon.png)mdms-mgramseva/TaxPeriod.json at QA · egovernments/mdms-mgramseva](https://github.com/egovernments/mdms-mgramseva/blob/QA/data/pb/BillingService/TaxPeriod.json)

Define the taxhead in the below mdms file for the business service which are allowed in echallan service.[ ![](https://github.com/fluidicon.png)mdms-mgramseva/TaxHeadMaster.json at QA · egovernments/mdms-mgramseva](https://github.com/egovernments/mdms-mgramseva/blob/QA/data/pb/BillingService/TaxHeadMaster.json)

Define the action and role action mapping for the API’s in the below mdms files.[ ![](https://github.com/fluidicon.png)mdms-mgramseva/actions-test.json at QA · egovernments/mdms-mgramseva](https://github.com/egovernments/mdms-mgramseva/blob/QA/data/pb/ACCESSCONTROL-ACTIONS-TEST/actions-test.json)  
[![](https://github.com/fluidicon.png)mdms-mgramseva/roleactions.json at QA · egovernments/mdms-mgramseva](https://github.com/egovernments/mdms-mgramseva/blob/QA/data/pb/ACCESSCONTROL-ROLEACTIONS/roleactions.json)

## Deployment Details

1. Add MDMS configs required for eChallan Service and calculator and restart MDMS service.
2. Deploy the latest version of eChallan Service and calculator.
3. Add eChallan Service persister yaml path in persister configuration and restart persister service
4. Add Role-Action mapping for APIs.

## Integration

### **Integration Scope**

echallan-calculator will be integrated with echallan-services. echallan-services internally invoke the echallan-calculator service to calculate and generate demand for the echallan request.

### **Integration Benefits**

eChallan calculator application is used to calculate the eChallan Fees based on the data mentioned in echallan creation. Based on the tax amount mentioned in echallan, demand is created.  So because of eChallan calculator, the calculation and demand generation logic will be separated out from eChallan services.

So in future, if calculation logic needs to modify then changes can be carried out for each implementation without modifying the eChallan services.

### **Steps to Integration**

eChallan service application needs to call `echallan-calculator/v1/_calculate`  API to calculate and generate the demand for the eChallan application.

## Interaction Diagram

TBD

## Reference Docs

### **Doc Links**

| **Title**  | **Link** |
| :--- | :--- |
| API Swagger Contract | [Swagger Document](https://editor.swagger.io/?url=https://raw.githubusercontent.com/egovernments/municipal-services/master/docs/e-Challan-v1.0.0.yaml#!/) |
| eChallan Service Document | [eChallans Service](https://digit-discuss.atlassian.net/l/c/4PDUeFf8) |

### **API List**

|  | **Link** |
| :--- | :--- |
| `echallan-calculator/v1/_calculate` | [https://www.getpostman.com/collections/773565d7b5866f0851e3](https://www.getpostman.com/collections/773565d7b5866f0851e3) |

