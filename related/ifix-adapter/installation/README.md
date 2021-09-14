# Installation

## Deployment of iFix Adapter <a id="deploy-mgramseva"></a>

Post infra setup \(Kubernetes Cluster\), the deployment has got 2 stages and 2 modes. We can see the stages first and then the modes.‌

### The 2 Modes of Deployment <a id="the-2-modes-of-deployment"></a>

Essentially,  iFix adapter deployment means that we need to generate Kubernetes manifests for each individual service. We use the tool called helm, which is an easy, effective and customizable packaging and deployment solution. So depending on where and which env you initiate the deployment there are 2 modes that you can deploy.‌

1. From [**local machine**](../../mgramseva/installation/local-setup.md) - whatever we are trying in this sample exercise so far.
2. Advanced: ****[**Setup CI/CD System**](../../mgramseva/installation/ci-cd.md) like Jenkins - Depending on how you want to setup your CI/CD and the expertise the steps will vary, however here you can find how we eGov has set up a exemplar CI/CD on Jenkins and the pipelines are created automatically without any manual intervention.

