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



## 2. Deployment <a id="2-deploy-digit"></a>

{% page-ref page="ifix-deployment-1.md" %}

{% page-ref page="mgramseva-deployment.md" %}



## 3. Destroy the Cluster <a id="5-destroy-the-cluster"></a>

Post validating the PGR functionality share the API response of the following request to assess the correctness of successful DIGIT PGR Deployment.

Finally, cleanup the DIGIT Setup if you wish, using the following command. This will delete the entire cluster and other cloud resources that were provisioned for the DIGIT Setup.

```text
cd DIGIT-DevOps/infra-as-code/terraform/my-digit-eks
terraformdestroy​
```

## Conclusion: <a id="conclusion"></a>

All Done, we have successfully Created infra on Cloud, Deployed Digit in the cluster.

