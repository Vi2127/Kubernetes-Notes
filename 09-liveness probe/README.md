* In order to verify if a container in a pod is healthy and ready to serve trafic, K8s provides for a range of healthy checking mechanism.

* Health checks or probes are carried out by the kubelet to determine when to recreate a container(for liveness probe) and used by service and deployments to determine if a pod should receive traffic.

* For example: Liveness Probes could catch a deadloack, where an app is running but unable to make progress. Recreating a container in such a state can help to make the application more available despite bugs.

* For running health-check, we would use cmds specifics to the application.

* If the cmd succeeds, it returns 0 and the kubectl conside the container to be alive and healthy. If the cmd returns a non-zero value the kubelet kills the pod and recreate it.

-----------------------------------------------------------------------------------------------

### To get details of pod (including liveness probe)
kubectl get pod <pod-name>
In details, there we will get section of Liveness under Containers, and all other info we can see there itself  
