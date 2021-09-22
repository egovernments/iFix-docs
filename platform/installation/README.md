---
description: iFix Infra Setup & Deployment
---

# Installation

## Deployment

The simplest way to get started with the **deployment process** is to manage deployment **configuration as code**. Each service deployment configuration is defined as Helm charts and deployed into the Kubernetes cluster. We can collocate the deployment-as-code as source code, leveraging all the benefits of source control including change tracking and branching, then package it. So below is the source code repo that contains all the deployment-as-code for iFix.

#### 1. mGramSeva Installation

{% page-ref page="../../related/mgramseva/installation/" %}

#### 2. iFix-adapter Installation

{% page-ref page="../../related/ifix-adapter/installation/" %}

#### 3. iFix Dashboard Installation

{% page-ref page="../../related/ifix-dashboard/installation.md" %}

## Pre-reads <a id="pre-read"></a>

* Know the basics of Kubernetes: [https://www.youtube.com/watch?v=PH-2FfFD2PU&t=3s](https://www.youtube.com/watch?v=PH-2FfFD2PU&t=3s)
* Know the [basics of kubectl](https://www.tutorialspoint.com/kubernetes/kubernetes_kubectl_commands.htm) commands
* Know Kubernetes manifests: [https://www.youtube.com/watch?v=ohSUtEfDefc](https://www.youtube.com/watch?v=ohSUtEfDefc)
* Know how to manage env values, secrets of any service deployed in Kubernetes [https://www.youtube.com/watch?v=OW244LxB4oI](https://www.youtube.com/watch?v=OW244LxB4oI)
* Know how to port forward to a pod running inside k8s cluster and work locally [https://www.youtube.com/watch?v=TT3nd5n5Yus](https://www.youtube.com/watch?v=TT3nd5n5Yus)
* Know sops to secure your keys/creds: [https://www.youtube.com/watch?v=DWzJ87KbwxA](https://www.youtube.com/watch?v=DWzJ87KbwxA)

## 1. Deployment Architecture <a id="v-1-choose-the-cloud"></a>

![](https://lh4.googleusercontent.com/JkymqACmPBvb3Y77UrqghaQifq1YYC_IfujLtK9eaXcIcMwvkBBx0thuGO7UD2BssAflbyyE2u9teNkqKLywDet09cl0fVO6GfgqFnRjUIRSLahvj5v7mT97sl8MKuYcFj2qfntM8Zs=s0)

## 2. Choose the Install Type <a id="v-1-choose-the-cloud"></a>

Choose your cloud and follow the Instruction to set up a Kubernetes cluster before moving on to the Deployment.

{% page-ref page="infra-setup/on-azure.md" %}

## 3. Deployment-as-code

## 4. Destroy the Setup <a id="5-destroy-the-cluster"></a>

Finally, clean up the cluster Setup if you wish, using the following command. This will delete the entire cluster and other cloud resources that were provisioned for the DIGIT Setup.

```text
cd DIGIT-DevOps/infra-as-code/terraform/my-ifix-eks
terraformdestroy​
```

## Conclusion <a id="conclusion"></a>

All Done. We have successfully Created infra on Local, Cloud, Deployed iFix into the Kubernetes cluster.

