* *Namespace*: A namespace is a group of related elements that each have a unique name or identifier. Namespace is used to uniquely identify one or more names from other similar name of different objects, groups or the namespace in general.

* K8s namespaces help different projects, teams or customers to share k8s cluster & provides:
 1. A scope for every names
 2. A machanism  to attach authorization and policy to a subsection of the cluster

* By *default*, a k8s cluster will instantiate a default namespace when provisioning the cluster to hold the default set of pods, Services and Deployments used by the cluster.

* we can use *Resource Quota* on specifying how many resouces each namespace can use.

* Most of resources (eg: pods, services, replication controller and others) are in namespace and low-level resources such as nodes, PV are not in any namespace


---------------------------------------------------------------------------
### To get namespace
kubectl get namespaces

### To run namespace manifest file
kubectl apply -f <namespace.yml> 

* -n <namespace> will not mention then resource will create in default namespace
### To apply changes of manifest file in "dev" namespace
kubectl apply -f <test-pod.yml> -n dev

### To delete pod
kubectl delete -f <manifest-file_name.yml> -n dev

### To change default namespace to "dev" or "any other" namespace
kubectl config set-context $(kubectl config current-context) --namespace=dev
*this command will change valuse in k8s configuration file.



