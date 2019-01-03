# Overview

Using minikube for the K8 playground.

This repo contains:
- Few commands for daily usage with kubectl
- Playground for deployments 
- (Soon) Helm charts playground

## Useful Commands 
```
 # Returns all available running pods
kubectl get pods

# Details for a POD
kubectl describe pod <name of the pod> 

# Expose a deployment to outside world
kubectl expose <type name eg. deployment> <identifier/name> --port=(external port) --target-port=(container-port) --type=(service-type)  # expose a deployme to outside world

# Useful for remote clusters
kubectl port-forward <pod name> [LOCAL_PORT:REMOTE_PORT] # useful for remote clusters

# Attach pod
kubectl attach <pod name> -c <container>

# Bash access to a pod
kubectl exec [-it] <pod name> [-c CONTAINER] -- COMMAND [tags ..] 

# Update labels on a resource
kubectl label [--overwrite] <type> KEY_1=VAL1... 

# Run an image
kubectl run <name> --image=image

# for scaling a deployment
kubectl scale --replicas=<num> deployment/<name of deployment> 

# Return all the available deployments
kubectl get deployment

# Updating the service when Scaling with a LoadBalancer deployment
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


