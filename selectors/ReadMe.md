Selectors:
-----------------------
3 Nodes or 2 Nodes
apply --> EKS is randomly selecting the nodes

apply labels to the nodes

then we use the nodeselector in pod definition.

# kubectl label nodes <node-name> tier=web
# kubectl get nodes --show-labels

requiredDuringSchedulingIgnoredDuringExecution
1. Scheduler will schedule based on labels -- hard rule
2. Before POD comes to execution, som one may change  node labels or may not change.

preferedDuringSchedulingIgnoredDuringExecution:
1. Scheduler will schedule based on labels -- soft rule
2. Before POD comes to execution, som one may change  node labels or may not change.

You can have multiple labels, you can put weight
if multiple nodes matches, more wieght will get prefered.

Podaffinity:
-----------
Cart --> Catalogue

If both pods are in same node, latency will be less.
catalogue --> labels
cart --> go and sit in the node where catalogue is running

Anti Affinity:
-------------
catalogue is running
I want cart in node where catalogue is not running.

Use Case:
-----------------
Redis  --> Cache DB

Web Application --> Redis DB

1. First replica it goes to node where already redis is not running
    3 Nodes -->  select 1 Node
2. Select another node 2
3. 3ed Node


Taint and tolerations:
-----------------------
Taint  == paint

If you taint a node , you don't want any pods in that node.

out of 3 nodes taint one node , by default scheudler will not schedule any pod in this.

But we want DB pods in this node. For this we should use toleration.












