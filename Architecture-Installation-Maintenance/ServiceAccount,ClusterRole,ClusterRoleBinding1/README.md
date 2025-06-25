## KillerCoda: [link](https://killercoda.com/sachin/course/CKA/sa-cr-crb-1)
## Video: [link](https://www.loom.com/share/b9f860c5a40a49a2a3940a3090fad33d?sid=10251aaa-0ac0-4a0c-bae4-b239dfc757b3)
## Name: Service Account, Cluster Role, Cluster Role Bindings 1 
## Run the below command

CREATE SERVICE ACCOUNT
```
kubectl create sa app-account

```

CREATE CLUSTERROLE
```
kubectl create clusterrole app-role-cka --verb=get --resource=pods

```

CREATE CLUSTERROLEBINDING
```
k create clusterrolebinding app-role-binding-cka --clusterrole app-role-cka --serviceaccount app-account

```
