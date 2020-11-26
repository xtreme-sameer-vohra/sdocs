# Certification Details

Certified Kubernetes Application Developer: https://www.cncf.io/certification/ckad/

Candidate Handbook: https://www.cncf.io/certification/candidate-handbook

Exam Tips: https://www2.thelinuxfoundation.org/ckad-tips



Keep the code - DEVOPS15 - handy while registering for the CKA or CKAD exams at Linux Foundation to get a 15% discount.


# Component s

## Node
Runs the containers deployed on K8s. It is the worker

### Kubelet
Agent running on the node that monitors health of pods and running pods on the container runtime

### Container Runtime
Engine that runs the containers

## Master
Handles all requests and is the brains that orchestrates work on the workers

### API Server
Receives all incoming API requests and is the frontend to K8s cluster

### Controller
The brains, ensure that what the cluster is running and what is desired keep converging

### Scheduler
Assigns work to the Nodes based on their capacity and work affinity

### Etcd Service
Key/value store that is used for all state in K8s cluster
Holds locks for distributed work 


# Kubectl commands

## Kubectl reference conventions - https://kubernetes.io/docs/reference/kubectl/conventions/

kubectl run my-app # Looks like run is deprecated in favor of create for generating yaml

### Generate yml deployment template
kubectl create deployment --image=nginx nginx --dry-run -o yaml 


### Get Cluster Info
kubectl cluster-info

kubectl get nodes

# Concepts

## POD
Instance of an application
Smallest deployable unit

## YAML in K8s
### apiVersion - K8s version that defines object

### kind - type of object (eg Pod)

### metadata - name, labels

### spec - info pertaining to instantiating the 

### data (eg. Config Map)


# Misc
### Higher level abstractions
	- Replication Controller -> Replica Set
	- Replica Set extends the Replication Controller by adding `selector` 


### Dockerfile
	- `entrypoint` == `cmd` in pod
	- `cmd` == `args` in pod


## Taints
- assigned to a node and prevents pods that don't match from not being run there

## Tolerations
- allows a pod to be tolerant of a taint applied to a node. This doesn't mean that the pod will always be scheduled on a matching node.

## NodeSelector
- simple mechanism for landing pods on a node

## NodeAffinity
- more complex than nodeSelector, allows more complex rules (match item in array eg. size: small,medium,large)

## Readiness Probes
- By default K8s will consider a pod ready as soon as containers are created. Readiness probes allows a more finer grained control
	- http
	- tcp
	- exec commmand
	
## Liveness Probes
	- similar to readiness probes but used after the application is considered started

## Services
	3 types

	NodePort - assigns that nodePort on every node so that a service can be accessed via the node IP
	clusterIP - the default, picks an IP from the pod CIDR and uses that for the service
	Loadbalancer - uses the external IaaS to create a loadbalancer


## Ingress
	More advanced solution compared to service to handle path based routing, host based routing, etc to multiple pods 

## Network Policies
	Firewall rules for a cluster


Make sure you check out these tips and tricks from other students who have cleared the exam

https://www.linkedin.com/pulse/my-ckad-exam-experience-atharva-chauthaiwale/

https://medium.com/@harioverhere/ckad-certified-kubernetes-application-developer-my-journey-3afb0901014

https://github.com/lucassha/CKAD-resources







# Exam Prep

## VIMRC
 ~/.vimrc file with the following content:
:set nu
:set et
:set sw=2 ts=2 sts=2

set list
set listchars=tab:>-

:retab

## Namespace
k config set-context --current --namespace=default

## Alias
alias k=kubectl

## Export
export do="--dry-run=client -o yaml"

