# Kubernetes
##
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
 `ssh -i ~/.minikube/machines/htominikube/id_rsa docker@$(minikube ip)`

To get the url for connection to a deploymente :
minikube service <service name> 
minikube service <service name> --url ; to get just the url


## kubectl Commands  // alias k=kubectl
- kubectl cluster-info
- kubectl exec
- kubectl pc 
- kubectl get nodes
- kubectl get pods > list of pods in default namespace
- kubectl get namespaces  > list of namespaces
- kubectl get pods --namespace=<namespace> > list pods in an specific namesapce
- kubectl run <name of the pod> --image=<name of the image> > to create a pod
- kubectl describe pod <podname> 
- kubectl get pods -o wide
- kubectl delete pod <podna
## Deployment

A Kubernete deployment is used to tell Kubernetes how to create or modify instances of the pods that hold a containerized application. Deployments can scale the number of replica pods, enable rollout of updated code in a controlled manner, or roll back to an earlier deployment version if necessary.


- kubectl create deployment <deployment name> --image=<image name>
- kubectl get deployment  > list of deployments
- kubectl describe deployment <name of the deployment> show the details about an specific deployment
- kubectl scale deployment <deployment name> --replicas=<number of replicas>  > scale in/out the deployment 
- kubectl delete deployment <deployment name> deletes a deployment
- 

notes:  
- Selector : is used to connect pods with deployments 
- ReplicaSet: purpose is to maintain a stable set of replica Pods running at any given time

## Services

- A service in Kubernetes is an abstract way to expose an application running on a set of pods as a network service 

- a Service groups together a number of pods that perform the same function and presents them as a single entity.  

-ClusterIP
-Load Balancer 
-Node Port

**Commands** 

- kubectl expose deployment <deployment name> --port=< external port number> --target-port=<internal port number>  > espose the internal services to a given port.
- kubectl get services (SVC)  > shows a list of services 
- kubect describe service <service name>  > shows the details about an expecific service 
- kubectl delete service <service name> deletes a service  

note : 
--type=NodePort 
--type=LoadBalancer 

StrategyType
## Storage 


Kubernetes supports many types of volumes. A Pod can use any number of volume types simultaneously. Ephemeral volume types have a lifetime of a pod, but persistent volumes exist beyond the lifetime of a pod. When a pod ceases to exist, Kubernetes destroys ephemeral volumes; however, Kubernetes does not destroy persistent volumes. For any kind of volume in a given pod, data is preserved across container restarts.

