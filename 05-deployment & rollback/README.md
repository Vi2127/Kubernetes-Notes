* A ReplicaSet cannot perform updates or rollbacks by itself.

* This is where the Deployment object comes into play.

* The Deployment object acts as a supervisor for pods with the assistance of a ReplicaSet.

* It initiates the creation of a ReplicaSet, and the ReplicaSet executes the instructions specified in the manifest file.

* Each change in the manifest file results in the creation of a new ReplicaSet.

* The old ReplicaSet ceases operations but remains as the previous version, allowing for later rollback or version change.

* Upon rollback, the ReplicaSet reverts to the previous (or specified) revision, while the number of replicas (pods) remains the same as the previous ReplicaSet.

* Deployment can be paused to apply multiple fixes to its pod template spec.

* Older ReplicaSets that are no longer necessary can be cleaned up.

**** Reason of getting fail of deployment
* Insufficient quota.
* Readiness probe failures.
* Image pull error.
* Insufficient permission.
* Limit range
* Application runtime misconfiguration.

----------------------------------------------------------------------------------------------------------------------------------

### To rollback to previous or any revision
kubectl rollout undo deploy/<deployment-name> --to-revision=2(REVISION NUMBER)

### To get deployment details
-> kubectl get deploy
o/p: Name, Ready, Up-to-date, Age

### To check, how deployment creates replica set and pods
-> kubectl describe deploy <deployment-name>

### To scale up and scale down
-> kubectl scale --replicas=4 deploy <deployment-name>

### To check status
-> kubectl rollout status deploy <deployment-name>

### To check history or versions.
-> kubectl rollout history deployment <deployment-name>

### To rollout previous version
-> kubectl rollout undo deployment <deployment-name>
