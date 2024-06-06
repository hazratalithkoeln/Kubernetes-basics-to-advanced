# Kubernetes Basics to Advanced

Kubernetes is an open-source container orchestration system for automating software deployment, scaling, and management.
Today, Kubernetes is widely used in production to manage Docker and essentially any other type of container runtime. While Docker includes its own orchestration tool, called Docker Swarm, most developers choose Kubernetes container orchestration instead.

## Why Kubernetes?

1. Cluster
2. Auto-healing
3. Auto-scaling
4. Multiple enterprises support.
   
### Note: 
Docker does not have this support.

Control plane (master node):

API server: It exposes basically Kubernetes to the other world. It takes all the requests from external worlds.

etcd: It is basically a key value store. The entire Kubernetes cluster information is stored as objects that are key-value pairs inside this, etcd.

Scheduler: responsible for scheduling the pods or scheduling the resources of Kubernetes. It is receiving the information from an API server.

Controller manager: This controls the replica set. Manage the Kubernetes in-build controller.

Example: replica set

Cloud controller manager (CCM): This is an open-source utility. If you have on-premises service, then this component is not required.

Data plane (worker node):

Kubelet: responsible for maintaining, creating, or running a pod. If pods are not running, then they will take the necessary actions using the Kubernetes control plane.

Kube-Proxy: Provide networking, like generating the IP address or load-balancing. Basically, it uses IP tables on your Linux machine. When we want to use auto-scaling, then this service will create a network between pods.

Container runtime: responsible for running a container.
