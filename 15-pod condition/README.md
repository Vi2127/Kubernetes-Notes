* *Pending:*
* The pod has been accepted by the k8s system but its not running.
* If pod connot be schedule because of resource constraint.
* one or more of the containers images is still downloading.

* *Running:*
*All of the containers have been created.

* *Succeeded:*
* All containers in the pod have terminated in success, and will not be restarted.

* *Failed:*
* All container in the pod have terminated
* the container either exited with non-zero status.

* *Unknown:*
* state of the pod could not be obtained
* due to an error in network or communicating with the host of the pods.

* *Completed:*
* The pod has run to completion as there's nothing to keep it running.

### To check details of pods
kubectl describe pod/<pod-name>

*Pod Conditions:*
1. PodScheduled: The pod has been schedule to a node
2 Ready: The pod is able to serve request and will be added to the load balancing pools
3. Initialized: All init containers have started successfully
4. Unscheduled: Due to lacking of Resources or other constraints
5. Containers Ready: All containers in the pod are ready.
