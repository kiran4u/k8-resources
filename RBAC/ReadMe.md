RBAC --> Role based access control
------------------------------

Admin Access

EKS adminitstrators

Project Team --> reboshop

Step 1:
-----------
1. Admin create cluster
2. Namespace will be created by admins


Role  --> admins will create one role for us
RoleBinding --> they willbind the role with permissions

Authentication
Authorization

EKS --> AWS
-------------
Authentication will be handled by AWS IAM
Authorization will be handled by  EKS Cluster.

1. We need to create one IAM user that can have authentication to EKS Cluster.
   create IAM user with read policy.

   User --> username, password
   Role --> what are the permisissions we have
   binding --> we will attach role to user.


   api-groups
   resources belong to api groups
   actions of resources --> create, read, update, delete


# Command to get auth details form kube-system namespace
kubectl get configmap aws-auth -n kube-system -o yaml

we need to edit aws-auth configmap in kube-system namespace to let EKS cluster know IAM users.

Now he will mail us, 
IAM user created 
roboshop namespace created
roboshop admin role created
attached IAM roboshop  admin user to the  roboshop amdin role
Configured aws-auth to add IAM user to EKS Cluster

Now go ahead and use your IAM user.

# New workstation
aws sts get-caller-identity
[ec2-user@ip-172-31-44-197 ~]$ aws eks update-kubeconfig --region ca-central-1 --name spot-cluster
Added new context arn:aws:eks:ca-central-1:601241527501:cluster/spot-cluster to /home/ec2-user/.kube/config

Created read only usr "kiran"

Usually DevOps engineers for Roboshop have namepsace admin access.
Now we have developers
they should not have admin access

they should only have limited access to deploy their microservices.

############
EKS Admins:
----------
Roboshop namespace
IAM group of developers
IAM group of namespace administrators
IAM group of  namespace readers

Role, RoleBinding, AWS-auth
ClusterRole, ClusterRoleBidning, AWS-auth   --> devops engineers
Projects may need some access to cluster level resources like PV

A new person addded to EKS-admin team
-------------------------------
ClusterRole
ClusterRoleBinding
------------------------------------------------------------------


Deployments
PV, PVC, 
StatefulSet,
Services.
------------------









