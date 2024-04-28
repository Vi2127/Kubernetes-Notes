* *Labels*: Labels are the mechanism we use to organise kubernetes objects. 
* It is similar to Tags.
* It is a key-value pair that attached to the objects.
* Multiple labels can be attach to an object.
* Once labels are attached to an object, we would need filter to narrow-down and these are called as *label selectors*
* api support two type of *selector* - Equality based (=, !=) and - Set based (in, notin, exists)
ex: kubectl get pods -l env=development
ex: kubectl get pods -l 'env in (dev, stage, prod)'


---------------------------------------------------------------------------------
### To apply changes
-> kubectl apply -f <manifest-file_name.yml>

### To see all labels
-> kubectl get pods --show-labels

### To assign label from command line
-> kubectl label pods <pod-name> <label-key>=<label-value>
ex: kubectl label pods <pod-name> myname=vijay

### To get pod based on labels
-> kubectl get pods -l env=development
-> kubectl get pods -l env!=development myname=vijay

### Delete pod using label
-> kubectl delete pod -l env!=development

