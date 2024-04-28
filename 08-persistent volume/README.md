* *Persistent Volume*: It is a cluster-wide resource that we can use to store data in a way that it persists beyond the lifetime of a pods.

* *Persistent means Always available*

*The PV is not backed by locally attached storeage on a worker node but by networeked storage syatem such as EBS or NFS or a distributed file like Ceph

* K8s provide APIs for users and admin to manage the consume storage to manage the Volume, it uses the Persistent Volume API resource type and to consume it uses the Persistent Volume Claim API resource type.

* The PVC request a PV with your desired specification (Size, access mode, speed etc) fom k8s and once a suitable persistent volume is found it is bound to PVC.

* Once if user finishes its works, the attached PV can be released.

* The underlying PV can there be reclaimed and recycled(use by any other pod) for future usage. 

* *Restrictions:*
1. The nodes on which pods are running must be aws EC2 instances
2. Those instacnes need to be in the same region and availability Zone as the EBS volume
3. EBS only support a single EC2 instance mounting a volume.

* First Create PV ---> Create PVC ----> Create deployment and use PVC in it (to utilize the claimed volume)

-----------------------------------------------------------------------------------------

### To apply changes of manifest file
kubectl apply -f <manifest_file_name.yml>

### To check details of PV
kubectl get pv

## To check pvc
kubectl get pvc

