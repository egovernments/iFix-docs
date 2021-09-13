# iFIX Adapter

iFIX Adapter enables existing or new source systems to integrate seamlessly with iFIX. iFIX Adapter has been developed as a reference implementation for developers of source systems who want to integrate their departmental system with iFIX. 

iFix Adapter works as mediator between iFIX and its clients. This system will receive requests from client system and convert the data in the iFIX fiscal event or associated formats. 

### Pre-requisites.  <a id="Pre-requisites."></a>

Before you proceed with the configuration, make sure the following pre-requisites are met -

* _Java 8_
* Kafka server is up and running
* PSQL server is running
* Redis
* Following services should be up and running:
  * Client Service Like mgramseva-ifix-adapter
  * Target service IFIX- fiscal-event-service
  * Target Service IFIX-keycloak

### Key Functionalities <a id="Key-Functionalities"></a>

* iFIX client requests pushed to IFIX
* Auth token is fetched from keycloak and cached. Token will be re fetched 5 minutes before expiry
* Every push to iFIX is recoded with http status
  * status series 200 series considered success
  * status 400 are marked client error and reported back to client
  * status 500 resubmitted by scheduler

### Deployment Details <a id="Deployment-Details"></a>

1. Update the keycloak credentials client-id and secrets in environment file
2. Map the coa in HeadCodeToCoaMapping.yml
3. Map project in ProjectMapping.yml
4. Deploy the latest version of ifix-reference-adapter

### Configuration Details <a id="Configuration-Details"></a>

1. Update Key cloak credentials in dev.yaml, qa.yaml, prod.yaml according to environment

### Interaction Diagram <a id="Interaction-Diagram"></a>

![](../../.gitbook/assets/image%20%2851%29.png)

