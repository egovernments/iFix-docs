# Local Setup

### The 2 Stages: <a id="the-2-stages"></a>

Essentially, there are 2 stages that should allow you to use the full potential of DeploymentConfig and pipeline-as-code.

**Stage 1: Clone the DevOps** [**repo**](https://github.com/egovernments/iFix-DevOps/)**, choose your iFix product branch as iFix-adapter.**‌

 **Prepare an &lt;**[**env.yaml**](https://github.com/egovernments/iFix-DevOps/blob/mgramseva/deploy-as-code/helm/environments/mgramseva-qa.yaml)**&gt; master config file, you can name this file as you wish which will have the following configurations, this env file need to be in line with your cluster name.**‌

* each service global, local env variables
* credentials, secrets \(You need to encrypt using [sops](https://github.com/mozilla/sops#updatekeys-command) and create a &lt;**env&gt;-secret.yaml** separately\)
* Number of replicas/scale of individual services \(Depending on whether dev or prod\)
* mdms, config repos \(Master Data, ULB, Tenant details, Users, etc\)
* sms g/w, email g/w, payment g/w
* GMap key \(In case you are using Google Map services in your PGR, PT, TL, etc\)
* S3 Bucket for Filestore
* URL/DNS on which the DIGIT will be exposed
* SSL Certificate for the above URL
* End-points configs \(Internal/external\)

**Stage 2: Run the iFix\_Adapter\_setup deployment script and simply answer the questions that it asks.**

```text
cd iFix-DevOps/deploy-as-code/egov-deployer

go run ifix_adapter_setup.go

#Be prepared for the following questions
1. Do you have the Kubernetes Setup?
2. Provide the path of the intented env kubeconfig file
3. Which version of the DIGIT that you want to install
4. What mGramSeva Modules that you choose to install (Choose PGR)
5. All, done, Now do you want to preview the deployment manifests 
6. Are you good to proceed with the DIGIT Installation

All Done.Essentially, DIGIT deployment means that we need to generate Kubernetes manifests for each individual service. We use the tool called helm, which is an easy, effective and customizable packaging and deployment solution. So depending on where and which env you initiate the deployment there are 2 modes that you can deploy.
```

###  <a id="the-2-modes-of-deployment"></a>

