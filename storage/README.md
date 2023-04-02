
volumes inside of k8:
------------

emptydir
hostpath - type of kuberntes volume 

daemon set:
----------
If you run damonset it make sure one pod runs on each and every node
useful to collect metrics and logs of node.

mounting configs maps as volumes
--------------------------
1. create configmap for files like nginx.conf
2. mount them as volumes
3. Use it for containers


Storage/volumes outside of k8:
----------------------------
drive/external hard disk
PV --> Persistent Volumes
PVC --> Persistent Volume Claim

static provisioning:
--------------------
you create the disk  --> manual
you need to have PV, PVC --> Both are the k8 objects and used  to manages external volumes using these two volumes.
PV -> declare the list of storage disks information
PVC -> Pod talks to PVC and PVC claim from PV (claiming means requesting for storage)

Life cycle policies:
---------------------
retain --> even your pod deleted, kubernetes will make sure data will not be deleted.
delete --> if pod deletes your data will be deleted
recycle --> your disk is not deleted but data is erased

Access Modes:
-----------------
RWO --> multipel pods, only one pod is allowed to write, remaining pods are for read.(useful for DB application)
RWM --> all pods can read & write
RO  --> only for reading the data

EBS static provisioning:
----------------------
If EC2 is in one AZ, EBS also should be in same AZ.










