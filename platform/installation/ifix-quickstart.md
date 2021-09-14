---
description: >-
  Quickstart Installation helps you jump start with the iFix basic installation
  steps with limited functionalities to test it standalone or on the local
  machine.
---

# Quickstart

iFix is a distributed microservice-based platform that comprises many services which are containerized as dockers, depending upon the required features we can run only those dockerized services on any container orchestration platform like docker compose, Kubernetes, etc.

Here in this Quickstart guide where we'll install basic services to get the platform up, before we setup iFix services, we'll create a lightweight Kubernetes cluster called [k3d](https://github.com/rancher/k3d) on a local machine with specified H/W requirements. The H/W requirements are listed below to ensure before we proceed further.

## **1. Infra Setup** <a id="1-infra-setup"></a>

**To provision a lightweight Kubernetes cluster, please follow the instructions below in context to your OS and install the k3d on your target machine.**

### **H/W or VM Size** <a id="h-w-or-vm-size"></a>

* min 4 vCPUs \(recommended 6vCPU\)
* min 8GiB of RAM \(recommended 12GB\)
* min 30GiB of HDD \(recommended 30GB+\)

### **Tools** <a id="tools"></a>

* **Linux distribution running in a VM or bare metal**

  * Ubuntu 18.04 or Debian 10 \(VM or bare metal\)
  * Install [Docker](https://docs.docker.com/engine/install/ubuntu/)​
  * ​[Install kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/) on Linux
  * Open terminal and Install k3d on Linux using the below command

  ```text
  wget -q -O - https://raw.githubusercontent.com/rancher/k3d/main/install.sh | bash
  ```

* **OSX or Mac**

  * ​[Docker Desktop](https://docs.docker.com/docker-for-mac/install/) local Kubernetes cluster enabled
  * ​[Install kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl-macos/) on Mac
  * Install k3d on Mac, on terminal use [Homebrew](https://brew.sh/) \(Homebrew is available for MacOS\) using the below command

  ```text
  brew install k3d
  ```

* **Windows 10 or above**

  * ​[Docker Desktop for windows](https://docs.docker.com/docker-for-windows/install/#system-requirements-for-wsl-2-backend) need to be installed
  * ​[Install kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl-windows/) on Windows
  * ​[Install Chocolatey](https://chocolatey.org/) package manager for windows
  * Install [GitBash](https://git-scm.com/download/win) as an alternative command prompt that allows most of the Linux commands on windows.
  * Now open gitbash and Install k3d on Windows using the below command

  ```text
  choco install k3d
  ```

### **Infra \(Kubernetes Cluster\) Creation** <a id="infra-kubernetes-cluster-creation"></a>

**Once the above prerequisites are met, run the following tasks depending upon your OS.**

* _\*\*_login/ssh into the machine, go to terminal/command prompt and run the following commands as an admin user.
* Create /Kube directory and change permission. To use this directory for persistent data mount. This means all the container logs, data will be stored here.

```text
 mkdir /kube
 chmod 777 /kube

 #if you are unable to create the /kube folder in the root
 # you can create it your user directory and provide the absolue path below
```

* Create a cluster with a single master node and 2 agents \(Worker Nodes\) and mount the pre**-**created directory \(for data persistence\).

```text
k3d cluster create --k3s-server-arg "--no-deploy=traefik" --agents 2 -v "/kube:/kube@agent[0,1]" -v "/kube:/kube@server[0]" --port "80:80@loadbalancer"
```

* When cluster creation is successful, Get the kubeconfig file, which will allow you to connect the to the cluster at any time.

```text
k3d kubeconfig get k3s-default > k3dconfig
kubectl config use-context k3d-k3s-default --kubeconfig=k3dconfig
```

* Verify the Cluster creation by running the following commands from your local machine where the kubectl is installed. It gives you the sample output as below

```text
root@ip:/# kubectl cluster-info

OutPut:
Kubernetes control plane is running at https://0.0.0.0:33931
CoreDNS is running at https://0.0.0.0:33931/api/v1/namespaces/kube-system/services/kube-dns:dns/proxy
Metrics-server is running at https://0.0.0.0:33931/api/v1/namespaces/kube-system/services/https:metrics-server:/proxy



root@ip:/# k3d cluster list
NAME          SERVERS   AGENTS   LOADBALANCER
k3s-default   1/1       2/2      true
```

* You can verify the workers' nodes created by using the following command.

```text
kubectl get nodes

Output:
NAME                       STATUS   ROLES                  AGE     VERSION
k3d-k3s-default-agent-0    Ready    <none>                 3d18h   v1.21.1+k3s1
k3d-k3s-default-agent-1    Ready    <none>                 3d18h   v1.21.1+k3s1
k3d-k3s-default-server-0   Ready    control-plane,master   3d18h   v1.21.1+k3s1


kubectl top nodes

Output:
W0625 07:56:24.588781   12810 top_node.go:119] Using json format to get metrics. Next release will switch to protocol-buffers, switch early by passing --use-protocol-buffers flag
NAME                       CPU(cores)   CPU%   MEMORY(bytes)   MEMORY%   
k3d-k3s-default-agent-0    547m         6%     1505Mi          9%        
k3d-k3s-default-agent-1    40m          0%     2175Mi          13%       
k3d-k3s-default-server-0   59m          0%     2286Mi          14%
```

If the above steps are completed successfully, your Cluster is now up and running ready to proceed with the DIGIT Deployment.

## **2. iFix Setup** <a id="2-digit-setup"></a>

Now that we have the Infra setup to proceed with the DIGIT Deployment. Following are the tools that need to be installed on the machine before proceeding with the DIGIT Services deployment.

**What we'll deploy in Quickstart:**

* iFix core platform services
* iFix backbone services
* iFix domain services 

### **Prerequisites** <a id="prerequisites"></a>

1. iFix uses [golang](https://golang.org/doc/install#download) \(required v1.13.3\) automated scripts to deploy the builds on to Kubernetes - [Linux](https://golang.org/dl/go1.13.3.linux-amd64.tar.gz) or [Windows](https://golang.org/dl/go1.13.3.windows-amd64.msi) or [Mac](https://golang.org/dl/go1.13.3.darwin-amd64.pkg)​
2. All iFix services are packaged using helm charts[ ![](https://helm.sh/img/favicon-152.png)Installing Helm](https://helm.sh/docs/intro/install/)​
3. ​[kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/) is a CLI to connect to the kubernetes cluster from your machine
4. Install [CURL](https://help.ubidots.com/en/articles/2165289-learn-how-to-install-run-curl-on-windows-macosx-linux) for making api calls
5. ​[Install Visualstudio](https://code.visualstudio.com/download) IDE Code for better code/configuration editing capabilities
6. All the iFix services deployment configurations are in [GitRepo](https://github.com/egovernments/DIGIT-DevOps) which you would need to [install git](https://docs.github.com/en/github/creating-cloning-and-archiving-repositories/cloning-a-repository-from-github/cloning-a-repository) and then [git clone](https://docs.github.com/en/github/creating-cloning-and-archiving-repositories/cloning-a-repository-from-github/cloning-a-repository) it to your local.
7. ​[Install Postman](https://www.postman.com/downloads/) to run some digit bootstrap scripts
8. Mongo Database
9. s3 bucket for Druid storage

```text
root@ip:/# git clone -b iFix-quickstart https://github.com/egovernments/iFix-DevOps
```

* After cloning the repo CD into the folder iFix-DevOps and type the "code ." command that will open the visual editor and opens all the files from the repo iFix-DevOps

```text
root@ip:/# cd iFix-DevOps
root@ip:DIGIT-DevOps# code .
```

* Update the druid bucket storage name.

```text
https://github.com/egovernments/iFix-DevOps/blob/iFix-quickstart/deploy-as-code/helm/charts/backbone-services/druid/values.yaml#L35
```

* Have look at the [sample deployment config file](https://github.com/egovernments/iFix-DevOps/blob/iFix-quickstart/deploy-as-code/helm/environments/quickstart-config.yaml) and [sample deployments secret file](https://github.com/egovernments/iFix-DevOps/blob/iFix-quickstart/deploy-as-code/helm/environments/quickstart-config-secrets.yaml) that needs to be configured as per any specific values according to your needs. 

```text
https://github.com/egovernments/iFix-DevOps/blob/iFix-quickstart/deploy-as-code/helm/environments/quickstart-config.yaml
https://github.com/egovernments/iFix-DevOps/blob/iFix-quickstart/deploy-as-code/helm/environments/quickstart-config-secrets.yaml
```

* Add the following entries in your host file /etc/hosts depending on your OS, instructions can be found [here](https://phoenixnap.com/kb/how-to-edit-hosts-file-in-windows-mac-or-linux).

```text
127.0.0.1 quickstart.local.ifix
```

### Deployment <a id="deployment"></a>

Once all the prerequisites set up is complete, go to the following repo, run the command and follow the instructions.

```text
root@ip:# cd iFix-DevOps/deploy-as-code/egov-deployer

root@ip:# go run iFix_setup.go

#Be prepared for the following questions
1. Do you have the Kubernetes Setup?
2. Provide the path of the intented env kubeconfig file
3. Which version of the DIGIT that you want to install - Choose "Quickstart"
4. What DIGIT Modules that you choose to install
5. All, done, Now do you want to preview the deployment manifests 
6. Are you good to proceed with the DIGIT Installation

All Done.
```

As mentioned in the [sample deployments secrets file](https://github.com/egovernments/iFix-DevOps/blob/iFix-quickstart/deploy-as-code/helm/environments/quickstart-config-secrets.yaml), olap module needs two separate DB's and users in the existing Postgres database \[Druid and metabase\]



