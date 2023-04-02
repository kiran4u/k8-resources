
volumes:
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
