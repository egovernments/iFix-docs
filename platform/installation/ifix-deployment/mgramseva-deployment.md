# mGramSeva-Deployment

## Deploy mGramSeva

Post infra setup \(Kubernetes Cluster\), the deployment has got 2 stages and 2 modes. We can see the stages first and then the modes. 

### The 2 Stages <a id="the-2-stages"></a>

**Stage 1:  Clone the DevOps** [**repo**](https://github.com/egovernments/iFix-DevOps/)**,  choose your Ifix product branch.** 

 **Prepare an &lt;**[**env.yaml**](https://github.com/egovernments/iFix-DevOps/blob/mgramseva/deploy-as-code/helm/environments/mgramseva-qa.yaml)**&gt; master config file, you can name this file as you wish which will have the following configurations, this env file need to be in line with your cluster name.**

* each service global, local env variables
* credentials, secrets \(You need to encrypt using [sops](https://github.com/mozilla/sops#updatekeys-command) and create a**-secret.yaml** separately\)
* Number of replicas/scale of individual services \(Depending on whether dev or prod\)
* mdms, config repos \(Master Data, ULB, Tenant details, Users, etc\)
* sms g/w, email g/w, payment g/w
* GMap key \(In case you are using Google Map services in your PGR, PT, TL, etc\)
* S3 Bucket for Filestore
* URL/DNS on which the DIGIT will be exposed
* SSL Certificate for the above URL
* End-points configs \(Internal/external\)

**Stage 2: Run the digit\_setup deployment script and simply answer the questions that it asks.**

```text
cd iFix-DevOps/deploy-as-code/egov-deployer

go run mgramseva_setup.go

#Be prepared for the following questions
1. Do you have the Kubernetes Setup?
2. Provide the path of the intented env kubeconfig file
3. Which version of the DIGIT that you want to install
4. What DIGIT Modules that you choose to install (Choose PGR)
5. All, done, Now do you want to preview the deployment manifests 
6. Are you good to proceed with the DIGIT Installation

All Done.Essentially, DIGIT deployment means that we need to generate Kubernetes manifests for each individual service. We use the tool called helm, which is an easy, effective and customizable packaging and deployment solution. So depending on where and which env you initiate the deployment there are 2 modes that you can deploy.
```



### The 2 Modes of Deployment

Essentially, DIGIT deployment means that we need to generate Kubernetes manifests for each individual service. We use the tool called helm, which is an easy, effective and customizable packaging and deployment solution. So depending on where and which env you initiate the deployment there are 2 modes that you can deploy.

1. From local machine - whatever we are trying in this sample exercise so far. 
2. Advanced: From CI/CD System like Jenkins - Depending on how you want to setup your CI/CD and the expertise the steps will vary, however [here]() you can find how we have setup CI/CD on Jenkins and the pipelines are created automatically without any manual intervention.

