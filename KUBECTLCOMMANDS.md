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

## To run port forwarding in backgorund

```sh
kubectl port-forward myp-pod 8081:8081 &

# With above command even if you exit the command prompt it will listening on the port in background

## To get the process id for the port listening, use bellow command and kill the process to release the port number

ps -ef | grep port-forward

## The above command will print the process id, take the respective pid and kill it
kill -9 <pid>
```

## Create pod using YAML and save the config in annotations

```sh
kubectl create -f my-pod.yml --save-config
```

## Get pod information in json or yml

```sh
kubectl get pod my-pod-name -o yml
```

## Describe pod

```sh
kubectl describe pod my-pod-name
```

## Create pods using apply command

```sh
kubectl apply -f my-pod.yml
```

## To see the labels on deployment

```sh
kubectl get deployments my-deployment --show-labels
```

## Create a secret and store securely in kubernetes

```sh
kubectl create secret generic my-secret --from-literal=pwd=my-password

kubectl create secret generic postgres-secret --from-literal=postgres-password=YOUR_PASSWORD_HERE

```

## Create a secret from a file

```sh
kubectl create secret generic my-secret --from-file=ssh-privatekey=~/.ssh/id_rsa --from-file=ssh-publickey=~/.ssh/id_rsa.pub
```

## Create a secret from a key pair(SSL/TSL)

```sh
kubectl create secret tls tls-secret --cert=path/to/tls.cert --key=path/to/tls.key
```

## To find current namespace

```sh
kubectl config view | grep namespace
```

## Change namespace in cluster

```sh
kubectl config set-context --current --namespace=my-namespace
```

## To find current cluster

```sh
kubectl config view | grep cluster
```

## To see available contexts

```sh
kubectl config get-contexts
```

## To change cluster

```sh
kubectl config use-context my-context
```




