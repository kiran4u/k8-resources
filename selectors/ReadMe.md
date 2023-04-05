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


