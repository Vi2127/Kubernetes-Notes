## Things to remember
* If more than one container is running within a single pod, they all share the same IP address.

## Commands
----------------------------------------------------------------------------------------------
### To apply/create deployment
-> kubectl apply -f <manifest-file_name.yml>  

### To see pods
-> kubectl get pods

### To see more detailed view (get ip address)
-> kubectl get pods -o wide 

### To check details of pods
-> kubectl describe pod <pod-name>

### To check what's running on pods (and logs)
-> kubectl logs -f <pod-name>
    * if more than 1 container is running on single pod
        -> kubectl logs -f <pod-name> -c <container-name>
    * for intraction with pod
        -> kubectl exec <pod-name> -it -c <container-name> -- /bin/bash  

### To delete pods
-> kubectl delete pod <pod-name>
-> kubectl delete -f <manifest-file_name>









