* Containers within a pod use networking to communicate via loopback (using localhost:80 as the port number).
* Communication between pods within the same node can be done using their IP address: curl IP-address:port_number.
* *Problem statement*: Pods can crash/fail anytime, and an identical pod will be created with its own IP address. In this case, the IP address will change every time, making it difficult to communicate between services (like frontend and backend), and it's challenging for users to remember the new IP address of the website each time.
* A Service is a logical bridge between pods and end-users, providing a virtual IP.
* The Virtual IP is not an actual IP, but its purpose is purely to forward traffic to one or more pods.
* Kube-proxy keeps the mapping between the Virtual IP and the pods up-to-date.
* Labels are used to select which pods are to be put under a service.
* Creating a service will create an endpoint to access the pods/application.
* Services can be exposed in different ways by specifying the type in the service spec (ClusterIP, NodePort, LoadBalancer, Headless).
* *Headless*: Creates several endpoints that are used to produce DNS records. Each DNS record is bound to a pod.
* The default service can run only on ports 30000 - 32767.
* The set of pods targeted by a service is usually determined by a selector.
* ClusterIP is the default service type.
* *ClusterIP*: Creates a connector for in-node communication. Exposes a virtual IP reachable from within the cluster.
* *NodePort*: NodePort builds on top of the ClusterIP Service and provides a way to expose a group of Pods to the outside world (outside that cluster).
* It will give port number, which can be use with EC2 instance public DNS to access pod application.
* Public_DNS:port_number -> NodePort -> Virtual IP of cluster (Cluster IP) -> pods available in cluster.
* Need to enable above port number for EC2 instance at security group level.

--------------------------------------------------------------------------------------------------------------------
### To apply/create service 
kubectl apply -f service.yml

### To get all service
kubectl get svc (or service)

### To check service is working:
curl <service-IP>:<pod-port>

### To get service details (port, cluster-ip, name)
kubectl get svc

### To check in details about service
kubectl describe svc <service-name>
