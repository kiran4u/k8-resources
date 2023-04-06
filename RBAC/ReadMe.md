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





