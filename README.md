# Kubernetes Getting Started

## Getting Started With Kubernetes

1. Containers and micro-services bring a whole new set of management challenges, Kubernetes to the rescue.

1. Kubernetes is a leading tool for managing containerized applications at scale and cloud native microservices app.

## Kubernetes Architecture

1. Kubernetes cluster consists of Masters, Nodes, Pods, Services, Deployment, API & API Server.

1. Kubernetes is a orchestrator for micro-services applications.

1. Masters are the brains of cluster, they are also called as Cluster Control Plane.

1. Nodes are where User and Business applications are deployed and report back to masters.

1. For application to be deployed and managed by Kubernetes we need to, containerize the app, wrap it in pod, for self healing & scaling we wrap pods in deployment. All these are steps defined in Yaml manifest file.

### Masters

1. A kubernetes cluster should have highly available multi master control plane.

1. There should be minimum 3 masters to reach consensus.

1. Leader will be making changes in the cluster to reach the desired state.

1. Master nodes should be linux machines.

1. In hosted kubernetes services like GKE, AKS, EKS, master nodes are hidden from us. But there is a highly available API Endpoint.

1. Do not run User and Business applications on the masters.

### Master Ops

#### API Server

1. Gateway to the clusters, only the master node to communicate with the cluster.

1. Exposes API(Rest).

1. Consumes JSON/YAML.

#### Cluster Store

1. Presists cluster state and config

1. Based on etcd distributed database.

1. Have recovery plans in place.

#### Controllers

1. Controllers of Controllers
    - Node Controller
    - Deployment Controller
    - Endpoint Controller

1. Watch loops

1. Reconcile observed state of the cluster with desired state.

#### Kube-Scheduler

1. Watches API Server for new tasks.

1. Assigns work to cluster nodes.

### Kubernetes Nodes

1. Nodes consists of Kublet, Container Runtime, Kube-proxy.

#### Kubelet

1. Main kubernets agent on the node.

1. Registers the node with cluster.

1. Nodes can linux or windows machine.

1. Scheduler can intelligently assign the work to the node.

1. Work in the kubernetes node comes as a pod.

1. Watches API server for work tasks(Pods).

1. Excecutes pods.

1. Reports back to Masters.

#### Container Runtimer

1. Can be Docker

1. Pluggable: Container Runtime Interface(CRI).
    - Docker, gVyser, Kata Container.

1. Low level container intelligence.

1. Building and starting containers.

#### Kube-proxy

1. Networking Component.

1. Pod IP address.

1. Basic load-balancing.

#### Virtual Kubelet

1. Node less Kubernetes.

1. Pods run on cloud's hosted container back-end.

### Declarative Model and Desired State

1. Declarative Model
    - Describe what you want in a manifest file(YAML)
    - Description of how things look like, but not the how to do things.

### Kubernetes Pods

1. Kubernetes runs or orchestrate containers only if they run inside pods.

1. We can run multiple containers in single pod.

1. Pods provide shared execution environment, file system, memory and IP.

1. To point to specific containers in the pod we should use unique ports.

1. Service mesh is a extra container in pods to manage the networking.

1. Pods deployment is atomic, all or nothing.

1. Containers in the pod are always scheduled to the same node.

1. We deploy pods via deploy controller, like deployment or stateful set, to get the scaling, self-healing capabilities. We can have ordered startup and custom networking.

### Stable Networking with Kubernetes

1. Containers runs in pods.

1. Rolling an update, scaling up and down generates new pods with new ips.

1. Kubernetes service object which is works as a basic load balancing, will take care of directing the requests to the new pods.

1. Service object is a YAML manifest file with Labels, which point to pods having the same labels.

1. Service use the labels as selector to find the pods to send requests.

1. Service send traffic only to healthy node.

1. Based on the session it will send traffic to the session created pod.

1. Can send traffic to endpoints outside the cluster.

### Deployment

### API and API Server

### Getting Kubernetes on laptop

```bash
# For Mac
brew install kubectl

# For windows powershell
Install-Script -Name 'install-kubectl' -Scope CurrentUser -Force
install-kubectl.ps1 c:\kubectl
```
