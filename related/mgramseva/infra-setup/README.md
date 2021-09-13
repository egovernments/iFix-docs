# Infra Setup

## Introduction

mGramSeva is microservices based distributed cloud-native application, it contains many microservices that together in order work for the scale and speed. Each of this context specific microservices are dockerized and deployed on a kubernetes infrastructure. It is essential to understand some of the key concepts, benefits and best practices of kubernetes platform before we understand the deployment of the mGramSeva.   

## Pre-read: <a id="pre-read"></a>

* Know the basics of Kubernetes: [https://www.youtube.com/watch?v=PH-2FfFD2PU&t=3s](https://www.youtube.com/watch?v=PH-2FfFD2PU&t=3s)​
* Know the [basics of kubectl](https://www.tutorialspoint.com/kubernetes/kubernetes_kubectl_commands.htm) commands
* Know kubernetes manifests: [https://www.youtube.com/watch?v=ohSUtEfDefc](https://www.youtube.com/watch?v=ohSUtEfDefc)​
* Know how to manage env values, secrets of any service deployed in kubernetes [https://www.youtube.com/watch?v=OW244LxB4oI](https://www.youtube.com/watch?v=OW244LxB4oI)​
* Know how to port forward to a pod running inside k8s cluster and work locally [https://www.youtube.com/watch?v=TT3nd5n5Yus](https://www.youtube.com/watch?v=TT3nd5n5Yus)​
* Know sops to secure your keys/creds: [https://www.youtube.com/watch?v=DWzJ87KbwxA](https://www.youtube.com/watch?v=DWzJ87KbwxA)​

## 1. Choose the Install Type <a id="v-1-choose-the-cloud-1"></a>

Choose you cloud and follow the Instruction to setup a Kubernetes cluster before moving on to the Deployment.

{% page-ref page="../../../platform/installation/ifix-quickstart.md" %}

{% page-ref page="../../../platform/installation/on-aws.md" %}

## 2. Deployment Architecture <a id="v-1-choose-the-cloud"></a>

Before we begin the deployment, it is important to understand the deployment architecture that starts from the source code to production ready.

![](https://lh4.googleusercontent.com/JkymqACmPBvb3Y77UrqghaQifq1YYC_IfujLtK9eaXcIcMwvkBBx0thuGO7UD2BssAflbyyE2u9teNkqKLywDet09cl0fVO6GfgqFnRjUIRSLahvj5v7mT97sl8MKuYcFj2qfntM8Zs=s0)

## 3. Deployment-as-code <a id="3-deployment-as-code"></a>



[Deployment/platform/installation/ifix-deployment-1](https://app.gitbook.com/@egov-digit/s/ifix/~/drafts/-Mi9dGyD982zFQXSCUd0/platform/installation/ifix-deployment-1/@merged)‌

## 4. Destroy the Setup <a id="5-destroy-the-cluster"></a>

Finally, cleanup the cluster Setup if you wish, using the following command. This will delete the entire cluster and other cloud resources that were provisioned for the mGramSeva Infra Setup.

```text
cd DIGIT-DevOps/infra-as-code/terraform/my-iFix-eksterraformdestroy​
```

‌

## Conclusion: <a id="conclusion"></a>

‌

All Done, we have successfully Created infra on Local, Cloud, Deployed iFix into kubernetes cluster.

