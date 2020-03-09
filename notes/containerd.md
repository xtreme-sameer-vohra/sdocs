
Runtime manager on top of runc

# Terms

- OCI - open container initiative
- CRI - container runtime interface
- 


# Questions
1. How do they bake in the CRI plugin into containerd ? How does it work for K8s? how can it be leverage for Concourse and its own pluginy things
	Looks like its using GRPC Interfaces. 
	The Plugin leverages the Go Client Interface to make calls to containerd

2. The client is a smart client that can pull/push images ? How do we leverage that in Concourse ?
	There are multiple subcomponents that can be extended via the GRPC interface
	These are connected dynamically by socket connections, so everything doesn't have to be built as a single binary (eg. using a custom snapshotter)

3. What are GRPC interfaces ? Is that something that we can leverage for better modularization in Concourse ? How are out of tree GRPC plugins included ? Could it be used for different metrics providers in Concourse ?
	The runtime plugin within containerd with `ctr install` is interesting - can load plugins dynamically ?