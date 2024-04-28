* k8s has the possibility to automatically scale pods based on observed CPU Utilization, which is *Horizontal Pod Autoscaling*

* Scaling can be done only for scalable objects like Controller, Deployment or Replica Set.

* HPA is implemented as a kubernetes API resource and a controller.

* The controller periodally adjust the number of replicas in a replication controller ordeployment to match the observed average CPU Utilization to the target specified by user.

* The HPA is implemented as a controlled loop with a period controlled by the Controller manager's HPA sync-period (default value 30 sec)

* During each period, the controller manager queries the resource utilization against the metrics specified in each HPA definition.

* default time for Cooldown period to wait before downscale operation is 5 min.

* Metric server needs to be deployed in the cluster to provide metrics.
### To install matric server
<$ wget -O metricserver.yml https://github.com/kubernetes-sigs/me...>

### add below line in metricserver.yml under deployment section under container under args under --cert
--kubectl-insecure-tls
apply metricserver.yml file after modification.

* metric-server pod will start inside "kube-system" namespace.
-----------------------------------------------------------------------------------------------

* After deploying manifest file run below command to enable autoscaling
### To run deployment manifest file and assign pod cpu threshold with min and max pods
kubectl autoscale deployment <deployment_name> --cpu-percent=20  --min=1 --max=10 

