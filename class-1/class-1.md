# Class 1 - Kubernetes Workshop

## What is Kubernetes?

System for running many different containers over multiple different machines

## Why use Kubernetes?
When you need to run many different containers with different images

## Development

- minikube (Command Line Tool) Used for managing the VM itself (LOCAL ONLY)
- kubectl Used for managing containers in the node

1. Install Kubectl
2. Install a VM driver virtualbox
3. Install minikube (brew install minikube)

```bash
minikube status
kubectl cluster-info
```

## Production

Managed solutions:
- Amazon Elastic Container Service for Kubernetes (EKS)
- Google Cloud Kubernetes Engine (GKE)

Config files in kubernetes are used to create objects. Install

Object Types:
- StatefulSet
- ReplicaController
- Pod
- Service (ClusterIp, NodePort, LoadBalancer, Ingress)

Pod -> Runs one or more closely related containers
Services -> Sets up networking in a Kubernetes Cluster

## Important Takeaways

- Kubernetes is a system to deploy containerized apps
- **Nodes** are individual machines (or vm's) that run containers
- **Masters** are machines (or vm's) with a set of programs to manage nodes
- Kubernetes didn't build our images - it got them from somewhere else
- Kubernetes (the master) decided where to run each container - each node can run a dissimilar set of containers
- To deploy something, we update the desired state of the master with a config file
- The master works constantly to meet your desired state

## Imperative Approach

- Create 3 containers using the multi-worker image
- Make another 2 containers with multi-worker
- Delete 1 container running multi-worker
- Those X number of containers should be networked to multi-redis
- Those X number of containers should be updated to use multi-redis v1.23

## Declarative Approach

- There should be 3 containers using the multi-worker
- There should be 5 containers using multi-worker
- There should be 4 containers using multi-worker
- There should be 4 containers using multi-worker networked to multi-redis