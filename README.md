Pod:  Sets:
-------
Now i want multiple replicas/pods?
Everytime I need to delete the old pod and recreate pod

To address this we have Replica Set:

ReplicaSet:
--------------
It can create multiple pods. Replica set guarantee always a desired no of pods running.


eg: nginx-dhr4
podname = [replicaset-name] - [random-name]

Problem: when there is a new version of application, you need to manually remove the replicaset manually and create again.

For this problem we have deployment.

Deployment:
----------
 eg: deployment name pattern: [deployment_name]- [replicaset]-[random-name]

 Pod is a subset of ReplicaSet.
 ReplicaSet is a subset of deployment.

1.  It needs to maintain zero downtime
2.  New update also should happen

 Rolling Update:
 --------------
 10 pods are running
 11th pod  with new version --> running
 it will remove 10th old pod
 12th pod with new version --> running
 it will remove 9th old pod
 .
 .
 .
 20th pod --> running
 1st pod --> remove

 Note: in this approach few versions of application will be running for sometime.

 Rolling Update Strategy 
 ----------------------------------

 CICD Processs:
 -------------

 cretae new dpeloyment
 check deployment sttaus

 if find --> end pipeline --> success

 if fails --> take deployment to previous version using below command:

 kubcetl rollout undo deploymnet/nginx-deploymnet --to-revision=3

 ----------------------------------------------










