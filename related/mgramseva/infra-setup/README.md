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

Before we begin the deployment, it is important to understand the deployment architecture that starts from the source code to production ready. Deploying and managing Kubernetes have emerged as a streamlined way to deploy containers in the Cloud Infrastructure. When running Kubernetes at scale, managing, operating, and scaling its infrastructure to maximize cluster utilization — without suffering from idle resources — can be a big challenge. There are too many your development team needs to manage and configure. This includes selecting the best instance type and size, determining when to scale up or down, and making sure all of the containers are scheduled and running on the best instances — and that is even before starting to think about cost resource optimization.

![](https://lh4.googleusercontent.com/JkymqACmPBvb3Y77UrqghaQifq1YYC_IfujLtK9eaXcIcMwvkBBx0thuGO7UD2BssAflbyyE2u9teNkqKLywDet09cl0fVO6GfgqFnRjUIRSLahvj5v7mT97sl8MKuYcFj2qfntM8Zs=s0)

## 3. Deployment Pipeline-as-code <a id="3-deployment-as-code"></a>

Pipeline as code is a practice of defining deployment pipelines through source code, such as Git. Pipeline as code is part of a larger “as code” movement that includes infrastructure as code. Teams can configure builds, tests, and deployment in code that is trackable and stored in a centralized source repository. Teams can use a declarative [YAML](https://about.gitlab.com/blog/2020/10/01/three-yaml-tips-better-pipelines/) approach or a vendor-specific programming language, such as Jenkins and Groovy, but the premise remains the same.

A pipeline as code file specifies the stages, jobs, and actions for a pipeline to perform. Because the file is versioned, changes in pipeline code can be tested in branches with the corresponding application release.

The pipeline as code model of creating continuous integration pipelines is an industry best practice, but deployment pipelines used to be created very differently. Below are the two different ways you can deploy the services with pipeline-as-code

{% page-ref page="../installation/local-setup.md" %}

{% page-ref page="../installation/ci-cd.md" %}

## 4. Destroy the Setup <a id="5-destroy-the-cluster"></a>

Finally, cleanup the cluster Setup if you wish, using the following command. This will delete the entire cluster and other cloud resources that were provisioned for the mGramSeva Infra Setup.

```text
cd DIGIT-DevOps/infra-as-code/terraform/my-iFix-eksterraformdestroy​
```

## Conclusion: <a id="conclusion"></a>

All Done, we have successfully Created infra on Local, Cloud, Deployed iFix into kubernetes cluster.

