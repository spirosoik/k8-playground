# Overview

Using minikube for the K8 playground.

This repo contains:
- Few commands for daily usage with kubectl
- Playground for deployments 
- (Soon) Helm charts playground

## Useful Commands 
```
kubectl get pods # returns all available running pods

kubectl describe pod <name of the pod> # details for POD

kubectl expose <type name eg. deployment> <identifier/name> --port=(external port) --target-port=(container-port) --type=(service-type)  # expose a deployme to outside world

kubectl port-forward <pod name> [LOCAL_PORT:REMOTE_PORT] # useful for remote clusters

kubectl attach <pod name> -c <container>

kubectl exec [-it] <pod name> [-c CONTAINER] -- COMMAND [tags ..] # bash access to a pod

kubectl label [--overwrite] <type> KEY_1=VAL1... # update labels on a resource

kubectl run <name> --image=image

kubectl scale --replicas=<num> deployment/<name of deployment> # for scaling a deployment

kubectl get deployment

# Updating the service when Scaling

kubectl expose deployment tomcat-deployment --type=LoadBalancer --port=8080 --target-port=8080 --name tomcat-load-balancer

kubectl describe services tomcat-load-balancer

# List deployments
kubectl get deployments

# View status of deployment roll outs
kubectl rollout status

# Set the image of a deployment
kubectl set image

# History of rollout
kubectl rollout history
```

## Labels & Selectors

```
kubectl label node minikube storageType=ssd
```

## Health Checks

- Rediness probes which determines when a POD is ready.
- Liveness probes which determines when a POD is healthy or unhealthy after it has become ready


