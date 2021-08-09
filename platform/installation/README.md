# Full Installation

## Pre-read: <a id="pre-read"></a>

* Know the basics of Kubernetes: [https://www.youtube.com/watch?v=PH-2FfFD2PU&t=3s](https://www.youtube.com/watch?v=PH-2FfFD2PU&t=3s)
* Know the [basics of kubectl](https://www.tutorialspoint.com/kubernetes/kubernetes_kubectl_commands.htm) commands
* Know kubernetes manifests: [https://www.youtube.com/watch?v=ohSUtEfDefc](https://www.youtube.com/watch?v=ohSUtEfDefc)
* Know how to manage env values, secrets of any service deployed in kubernetes [https://www.youtube.com/watch?v=OW244LxB4oI](https://www.youtube.com/watch?v=OW244LxB4oI)
* Know how to port forward to a pod running inside k8s cluster and work locally [https://www.youtube.com/watch?v=TT3nd5n5Yus](https://www.youtube.com/watch?v=TT3nd5n5Yus)
* Know sops to secure your keys/creds: [https://www.youtube.com/watch?v=DWzJ87KbwxA](https://www.youtube.com/watch?v=DWzJ87KbwxA)

## v1. Choose the Cloud <a id="v-1-choose-the-cloud"></a>

Choose you cloud and follow the Instruction to setup a Kubernetes cluster before moving on to the Deployment.

{% page-ref page="on-aws.md" %}



## 2. Deploy DIGIT <a id="2-deploy-digit"></a>

Post infra setup \(Kubernetes Cluster\), the deployment has got 2 stages and 2 modes. We can see the stages first and then the modes. As part of a sample exercise we can deploy PGR, however deployment steps are similar, just that the prerequisites will have to be configured accordingly.

### The 2 Stages <a id="the-2-stages"></a>

**Stage 1:  Clone the DevOps** [**repo**](https://github.com/egovernments/iFix-DevOps.git)**,  choose your respective product branch. For mgramseva product choose the mgramseva branch likewise for other products choose the respective branch.**

 **Prepare an &lt;**[**env.yaml**](https://github.com/egovernments/iFix-DevOps/blob/mgramseva/deploy-as-code/helm/environments/mgramseva-dev.yaml)**&gt; master config file, you can name this file as you wish which will have the following configurations, this env file need to be in line with your cluster name.**

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

1. From local machine - whatever we are trying in this sample exercise so far.
2. Advanced: From CI/CD System like Jenkins - Depending on how you want to setup your CI/CD and the expertise the steps will vary, however [here](https://develop.digit.org/setup/more-deploy-docs/deployment-key-concepts/cicd) you can find how we have setup CI/CD on Jenkins and the pipelines are created automatically without any manual intervention.

## 3. Post Deployment Steps <a id="3-post-deployment-steps"></a>

Post deployment, now the application will be accessible from the configured domain.

To try out PGR employee login, Lets create a sample tenant, city, user to login and assign LME employee role through the seed script

1. We have to do the [kubectl port-forwarding](https://phoenixnap.com/kb/kubectl-port-forward) of the **egov-user** service running from kubernetes cluster to your localhost, this will now give you access to egov-user service directly and interact with the api directly.

```text
kubectl port-forward svc/egov-user 8080:8080 -n egovForwarding from 127.0.0.1:8080 -> 8080Forwarding from [::1]:8080 -> 8080​
```

​

2. Seed the sample data

* Ensure you have the postman to run the following seed data api, if not [Install postman](https://www.postman.com/downloads/canary/) on your local
* Import the following postman collection into the postman and run it, this will have the seed data that enable sample test users and localisation data.
  * 

![](https://gblobscdn.gitbook.com/assets%2F-MEQnEQWBZ6Gjip-3pEg%2F-Mdw5VULroRohxHJZvd3%2F-Mdw7lqAe59Fc6senbxQ%2Fimage.png?alt=media&token=3705435f-d577-4253-a6b0-fc34bb6bf49d)

![](https://gblobscdn.gitbook.com/assets%2F-MEQnEQWBZ6Gjip-3pEg%2F-Mdw5VULroRohxHJZvd3%2F-Mdw8J0o80oUqY2M8ILN%2Fimage.png?alt=media&token=74431d93-e997-4d50-acce-11b15675ad96)

## 4. Assessment of the DIGIT Deployment <a id="4-assessment-of-the-digit-deployment"></a>

By now we have successfully completed the digit setup on cloud, use the URL that you mentioned in your env.yaml Eg: https://mysetup.digit.org and create a grievance to ensure the PGR module deployed is working fine. Refer the below product documentation for the steps.

**Credentials:**

1. Citizen: You can use your default mobile number \(9999999999\) to signin using the default Mobile OTP 123456.
2. Employee: Username: **GRO** and password: [**\[email protected\]**](https://develop.digit.org/cdn-cgi/l/email-protection)

Post grievance creation and assignment of the same to LME, capture the screenshot of the same and share it to ensure your setup is working fine.

## 5. Destroy the Cluster <a id="5-destroy-the-cluster"></a>

Post validating the PGR functionality share the API response of the following request to assess the correctness of successful DIGIT PGR Deployment.

Finally, cleanup the DIGIT Setup if you wish, using the following command. This will delete the entire cluster and other cloud resources that were provisioned for the DIGIT Setup.

```text
cd DIGIT-DevOps/infra-as-code/terraform/my-digit-eksterraform destroy​
```

## Conclusion: <a id="conclusion"></a>

All Done, we have successfully Created infra on Cloud, Deployed Digit, Bootstrapped DIGIT, Performed a Transaction on PGR and Finally Destroyed the cluster.

