
# Service Types: 3

1. ClusterIP : Internal to K8 cluster (pod to pod communication)
2. NodePort : For outside world open port on Node(Host)

USER --> NODE1:<NODE-PORT> --> Cluster IP --> Container
         NODE2:<NODE-PORT> --> Cluster IP --> Container

3. Load Balancers:
 Work only with AWS, Azure, GCP.

 
