* *Volume* has the same life span as the Pod, and it outlives the containers of the Pod. This allows data to be preserved acress container restarts.

* Volume is attached to a Pod and shared among the containers of that Pod.

* Volume type decide the properties of the directory, like size, content ete.

* Some example of volume types are:
  1. node-local type such as emptydir and hostpath
  2. file sharing types such as nfs
  3. cloud provider-specific type like elasticblockstore

* *EmptyDir*: use this when we wanted to share contents between multiple containers on the same pod & not to the host machine.

* Container is the pod can all read and write the same files in the *emptydir* volume, through that volume can be mounted at the same or different paths in each containers.

* *hostpath*: Use this when we want to access the content of a pod/container from host machine.

* A host path volume mounts a file or directory from the host node's filesystem into your pod.










-------------------------------------------------------------------------------------------