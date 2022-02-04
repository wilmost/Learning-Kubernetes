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

- Pods: Pods are the smallest deployable units of computing that you can create and manage in Kubernetes.  Pods are ephemeral in nature

- Services : A service in Kubernetes is an abstract way to expose an application running on a set of pods as a network service. A Service groups together a number of pods that perform the same function and presents them as a single entity.



Kubectl  : CLI tool to allows you to connect to a cluster a management the cluster remotely


## Running cluster local 

 - minikube : create Kubernetes cluster in a single node
 - virtual machine or container manager : virtualbox, vmware, docker, Hyper-V, parallels
 - kubectl: command line tool
```
https://kubernetes.io/docs/tasks/tools/ 
```
 minikube start --driver=docker
 minikube status
 minikube ip  

 to login ssh:

 `ssh -i ~/.minikube/machines/minikube/id_rsa docker@$(minikube ip)`



## Commands 
- kubectl cluster-info
- kubectl exec
- kubectl pc 
- kubectl get nodes
- kubectl get pods > list of pods in default namespace
- kubectl get namespaces  > list of namespaces
- kubectl get pods --namespace=<namespace> > list pods in an specific namesapce
- kubectl run <name of the pod> --image=<name of the image> > to create a pod
- kubectl describe pod <podname>


notes: 
lens 

