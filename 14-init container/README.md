* *Init Containers*: these are special container that run before containers in a pod.

* init containers always  run to completion.

* If a pod's init container fails k8s repeatedly restarts the pod until init container succeeds.

USE CASE:
 1. Seeding a database
 2. Delaying the application launch untill the dependecies are ready.
 3. Clone a git repository into a volume
 4. generate configuration file dynamically

### to check old logs
watch kubectl get pods