# KubeCtl Commands

## Get nodes available in cluster

```sh
kubectl get nodes
```

## To see pods on the cluster

```sh
kubectl get pod
```

## Get Services

```sh
kubectl get services
```

## Create Pod wrapped inside deployment

```sh
kubectl create deployment <deployment_name> --image=<docker_image_name>

Eg: kubectl create deployment nginx-deploy --image=nginx
```

## To see deployments

```sh
kubectl get deployment
```

## To see replica set creating using deployment, we don't create replica set directly

```sh
kubectl get replicaset
```

## To edit existing deployment object

```sh
kubectl edit deployment <deployment_name>

Eg: kubectl edit deployment nginx-deploy

# Edit will bring the existing pods and replica set down and bring up the new pods and replica set with new configuration
```

## Debugging logs

```sh
kubectl logs <pod_name>
```

## To log into pod interactive terminal

```sh
kubectl exec -it <pod_name> -- bin/bash
```

## To get more detailed infromation about Pod

```sh
kubectl describe pod <pod_name>
```

## Create Pod using run command

```sh
kubectl run my-pod --image=gurramh/department-service:v1.0.0
```

## To port forward from local port to cluster port

```sh
kubectl port-forward my-pod 8081:8081
```


