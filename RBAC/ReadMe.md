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

1. We need to create one IAM user that can have authentication to EKS Cluster
2. 
