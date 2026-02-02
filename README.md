# Kubernetes-RBAC 🔐

Kubernetes Role Based Access Control (RBAC) is a Kubernetes cluster security feature that follows the principle of least privilege. It is divided into 4 categories. RBAC is used for users, groups and service accounts.

Categories 
- Roles = defines permissions for namespaced resources 
- Role Bindings = binds to rolebindings, they can also be binded to cluster roles to move cluster reasources into a namespace 
- Cluster Roles = define permissions for cluster resources 
- Cluster Role Bindings = binds clusterroles to for the policy to take a affect

# Open Identification Connect OIDC 🪙

 RBAC can integrated Open Identification Connect OIDC. OIDC provides web identity tokens for temporary access and prevents AWS static credentials from being stored in containers. Creating production ready kubernetes security, HIPPA compliance and attack surface reduction  

Service Account 

 ```bash
 kubectl create sa dev-sa
 ```
 Role 

 ```bash 
 kubectl create role pod-reader --verb=get,list,watch --resource=pods
 ```
Service Account 

 ```bash
 kubectl create rolebinding pod-reader-binding --role=pod-reader --serviceaccount=default:dev-sa
 ```

![image alt](https://github.com/DMayrant/Kubernetes-RBAC/blob/main/Screenshot%202569-02-01%20at%2016.38.19.png?raw=true)

![image alt](https://github.com/DMayrant/Kubernetes-RBAC/blob/main/Screenshot%202569-02-01%20at%2016.38.46.png?raw=true)
