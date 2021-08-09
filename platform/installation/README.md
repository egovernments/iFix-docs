# Full Installation

## Pre-read: <a id="pre-read"></a>

* Know the basics of Kubernetes: [https://www.youtube.com/watch?v=PH-2FfFD2PU&t=3s](https://www.youtube.com/watch?v=PH-2FfFD2PU&t=3s)
* Know the [basics of kubectl](https://www.tutorialspoint.com/kubernetes/kubernetes_kubectl_commands.htm) commands
* Know kubernetes manifests: [https://www.youtube.com/watch?v=ohSUtEfDefc](https://www.youtube.com/watch?v=ohSUtEfDefc)
* Know how to manage env values, secrets of any service deployed in kubernetes [https://www.youtube.com/watch?v=OW244LxB4oI](https://www.youtube.com/watch?v=OW244LxB4oI)
* Know how to port forward to a pod running inside k8s cluster and work locally [https://www.youtube.com/watch?v=TT3nd5n5Yus](https://www.youtube.com/watch?v=TT3nd5n5Yus)
* Know sops to secure your keys/creds: [https://www.youtube.com/watch?v=DWzJ87KbwxA](https://www.youtube.com/watch?v=DWzJ87KbwxA)

## 1. Choose the Cloud <a id="v-1-choose-the-cloud"></a>

Choose you cloud and follow the Instruction to setup a Kubernetes cluster before moving on to the Deployment.

{% page-ref page="on-aws.md" %}



## 2. Deploy DIGIT <a id="2-deploy-digit"></a>

Post infra setup \(Kubernetes Cluster\), the deployment has got 2 stages and 2 modes. We can see the stages first and then the modes. As part of a sample exercise we can deploy PGR, however deployment steps are similar, just that the prerequisites will have to be configured accordingly.

### The 2 Stages <a id="the-2-stages"></a>

**Stage 1:  Clone the DevOps** [**repo**](https://github.com/egovernments/iFix-DevOps.git)**,  choose your respective product branch. For mgramseva product choose the mgramseva branch likewise for other products choose the respective branch.**

 **Prepare an &lt;**[**env.yaml**](https://github.com/egovernments/iFix-DevOps/blob/ifix/deploy-as-code/helm/environments/ifix-dev.yaml)**&gt; master config file, you can name this file as you wish which will have the following configurations, this env file need to be in line with your cluster name.**

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

go run digit_setup.go

#Be prepared for the following questions
1. Do you have the Kubernetes Setup?
2. Provide the path of the intented env kubeconfig file
3. Which version of the DIGIT that you want to install
4. What DIGIT Modules that you choose to install (Choose PGR)
5. All, done, Now do you want to preview the deployment manifests 
6. Are you good to proceed with the DIGIT Installation

All Done.Essentially, DIGIT deployment means that we need to generate Kubernetes manifests for each individual service. We use the tool called helm, which is an easy, effective and customizable packaging and deployment solution. So depending on where and which env you initiate the deployment there are 2 modes that you can deploy.
```

1. For CI/CD System like Jenkins - Depending on how you want to setup your CI/CD and the expertise the steps will vary, however [here](https://develop.digit.org/setup/more-deploy-docs/deployment-key-concepts/cicd) you can find how we have setup CI/CD on Jenkins and the pipelines are created automatically without any manual intervention.



## 5. Destroy the Cluster <a id="5-destroy-the-cluster"></a>

Post validating the PGR functionality share the API response of the following request to assess the correctness of successful DIGIT PGR Deployment.

Finally, cleanup the DIGIT Setup if you wish, using the following command. This will delete the entire cluster and other cloud resources that were provisioned for the DIGIT Setup.

```text
cd DIGIT-DevOps/infra-as-code/terraform/my-digit-eks
terraformdestroy​
```

## Conclusion: <a id="conclusion"></a>

All Done, we have successfully Created infra on Cloud, Deployed Digit in the cluster.

