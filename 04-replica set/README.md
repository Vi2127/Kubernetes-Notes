* A replication controller is a object  that enables us to create multiple pods, then make sure that number of pods always exist.

* If a pod created using replication controller will be automatically replaced if they  does crash, failed or terminated.

* It is recommended if you just want to make sure 1 pod continuously runs even system reboots.

* Replica set is next genration of replication controller

* Replica set also support set based selector

* Kind: replica set and apiVersion: apps/v1

-----------------------------------------------------------------------------------------------------
### To apply changes from file
-> kubectl apply -f <file-name.yml>

### To scale replicas by using command.
-> kubectl scale --replicas=8 rc -l <label-name> 

### To check available replica set
-> kubectl get rs

### To delete replica set
-> kubectl delete rs/<replicaset-name>


