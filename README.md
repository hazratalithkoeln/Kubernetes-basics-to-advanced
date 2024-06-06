# Kubernetes Basics to Advanced

Kubernetes is an open-source container orchestration system for automating software deployment, scaling, and management.
Today, Kubernetes is widely used in production to manage Docker and essentially any other type of container runtime. While Docker includes its own orchestration tool, called Docker Swarm, most developers choose Kubernetes container orchestration instead.

## Why Kubernetes?

1. Cluster
2. Auto-healing
3. Auto-scaling
4. Multiple enterprises support.
   
#### Note: Docker does not have this support.
## Kubernets architecture
### Control plane (master node):
1. API server: It exposes basically Kubernetes to the other world. It takes all the requests from external worlds.
2. etcd: It is basically a key value store. The entire Kubernetes cluster information is stored as objects that are key-value pairs inside this, etcd.
3. Scheduler: responsible for scheduling the pods or scheduling the resources of Kubernetes. It is receiving the information from an API server.
4. Controller manager: This controls the replica set. Manage the Kubernetes in-build controller.
5. Example: replica set
Cloud controller manager (CCM): This is an open-source utility. If you have on-premises service, then this component is not required.
### Data plane (worker node):
1. Kubelet: responsible for maintaining, creating, or running a pod. If pods are not running, then they will take the necessary actions using the Kubernetes control plane.
2. Kube-Proxy: Provide networking, like generating the IP address or load-balancing. Basically, it uses IP tables on your Linux machine. When we want to use auto-scaling, then this service will create a network between pods.
3. Container runtime: responsible for running a container.


## Pod
A pod is like a wrapper for a container. It works like a Docker container. Inside the pod, there will be a container. A pod can be a single container or a group of containers. In most cases, a pod has a single container. If you put a group of containers in a pod, then there will be some advantages. You can get access to the container application through the pod cluster IP (kube-proxy generates the cluster IP address.).

1. Kubernetes will allow you to do shared networking, share files, and share storage. Inside a single pod container, pods can talk to each other by using localhost.

## YAML file written for pods.
####  All Kubernetes Commands:https://kubernetes.io/de/docs/reference/kubectl/cheatsheet/
# Kubernetes Configurations

This repository contains Kubernetes configuration files for various resources.

## Nginx Pod Configuration

Below is the configuration for an Nginx Pod:

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: nginx
spec:
  containers:
  - name: nginx
    image: nginx:1.14.2
    ports:
    - containerPort: 80
