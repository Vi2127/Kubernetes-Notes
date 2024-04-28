* if more than one node is present then it will deploy pod on that node on which resource get available.
* we can attach label to node.
* once label is attached to node, use label selector to specify in manifest file to pods run on specific node.


----------------------------------------------------------------------------------
### To apply changes
-> kubectl apply -f <manifest-file_name.yml>

### To attach label to node
kubectl label nodes <node-name> hardware=t2-medium 








