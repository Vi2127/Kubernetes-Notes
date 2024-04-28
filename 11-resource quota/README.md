* Scheduler decides about which nodes to place pods, only if the node has enough CPU resources available to satisfy the Pod CPU request.

* CPU is specified in units of cores and memory is specified in unit of Bytes.

Two types of constraints can be set for each resource type- Request & Limits
* *Request* is the amount of that resource that the system will guarantee for the container and k8s will use this value to decide on which node to place the pod.

* *Limit* is the max amount of resources that k8s will allow the container to use. In the case that request is not set for a container, it default to limits. If limit is not set then if default to 0.

* CPU values are specified in 'milliCPU' and memory in MiB.
	1CPU = 1000MiCPU

### chaeck last point too
* Request = Not mention, Limit = Mention => Request = Limit
* Request = mention, Limit = not mention => Limit = default(assigned to cluster/namespace, unlimited->all assigned to cluster/namespace)

* *Resource Quota* can be apply on below resources:
 1. Compute (CPU)
 2. Memory 
 3. Storage

* *Two limitation of Resource Quota on namespace:*
 1. Ecery container that runs in the namespace must have its own CPU limit.
 2. The total amount of CPU used by all containers in the namespace must not exceed a specified limit.

* Default Range for a container (can't assign more than limit and less than request)
CPU:
	request(min) - 0.5
	limit(max)   - 01
Memory:
	request(min) - 500M
	limit(max)   - 01Gi
* Follow above value for manifest file

----------------------------------------------------------------------------------------------------------
### To get all pods
 kubectl get pods

### To check details of pods
 kubectl describe pods <pod-name>
 * In this detail we can check reques and limit which we set

