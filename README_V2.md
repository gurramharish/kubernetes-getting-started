# Kubernetes


## K8s Components

1. Deployment, Pod, Service, Ingress, Volumnes, Secrets, CongifMap, StatefulSet.`

## Worker Node

1. Runs multiple pods inside
1. Needs 3 processes to be installed
    * Container Run Time
    * Kube Proxy
        * Communications between nodes and pods
    * Kubelet
        * Schedules Pods
        * Interacts with container run time and node
        * Starts pods
## Master Node

1. How do you interact with this cluster, schedule pod, monitor, re-schedule/re-start pod ?

```ans
Ans: Master Node manages the cluster
```

1. Maintains the cluster
1. Needs 4 processes to be installed
    * API Server
        * Enables interaction with k8s cluster 
        * Cluster gateway
        * Gatekeeper for authentication
    * Scheduler
        * API Server passest he request for scheduling pod and sends to the worker nodes.
        * Scheduler is intelligent to find which node the pod should be deployed so the request is send to particular worker node based on how much resources your pod need and checks the available resources on each wroker node.

## Pod

1. Smallest unit of K8s
1. Abstraction over container
1. Usually 1 application per pod
1. Each pod gets its own IP address
