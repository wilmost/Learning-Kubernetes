# Kubernetes

### My path learning  **Kuberntes**


## Container orchestration

Container orchestration is the process of automating the deployment, management, scaling, and networking tasks of containers.


## What is Kubernetes?

Kubernetes is a portable, extensible, open-source platform for managing containerized workloads and services, that facilitates both declarative configuration and automation. 


## Kubernetes Components 

### **Control componentes** (Control plane)
  It is basically the brains of the entire cluster

- **kube-apiserver** : This acts as the entrance to the Kubernetes control plane, responsible for validating and processing requests delivered using client libraries. ej. `kubectl` program. 

- **etcd** : It holds configuration data and information about the state of the cluster (Distributed key-value store)

- **kube-controller-manager** : Resposible for controlling the state of the cluster.

- **kube-scheduler** : does the task of scheduling in Kubernetes making sure none of the servers in the cluster is overloaded. 


### **Node componentes**  (Node) : 
Responsable for running workloads.
- **kubelet** : This service acts as the gateway between the control plain and each of the nodes in a cluster.

- **kube-proxy** : Thi service runs on each node server and maintains network rules on them.

- **container runtime** : container runtime like Docker or rkt or cri-o.




## Kubernetes Objects 

Objects are persistent entities in the Kubernetes system. Kubernetes uses these entities to represent the state of your cluster

- Pods 

- Services


## Commands 

- kubctl exec
- kubctl pc 
- kubctl cordon

notes: 
lens 

