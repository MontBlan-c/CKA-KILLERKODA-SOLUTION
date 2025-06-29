## Group: Architecture, Installation & Maintenance
## Weight: 10
## Name: Cluster Upgrade
## KillerCoda: [link](https://killercoda.com/sachin/course/CKA/cluster-upgrade)
## Video: [link](https://www.loom.com/share/3d25001848514e0b8c2e3f9d32d28243?sid=a4a836f4-1fa4-4b35-8653-a66ba5dc5336)
# Below guide is for this question and if you wanna learn more about cluster upgrade  please refer below blog .
- [cluster-upgrade](https://anish60.hashnode.dev/upgrading-kubernetes-cluster)


# Find the all the available version of the kubeadm
```
apt update
apt-cache madison kubeadm
```

# Upgrading Control Plane


### Upgrade the kubeadm 

```sh

apt-mark unhold kubeadm && \
apt-get update && apt-get install -y kubeadm=1.30.1-1.1 && \
apt-mark hold kubeadm
```



### Verify that the download works and has the expected version:

```sh
kubeadm version
```

### Verify the upgrade plan:

```sh
kubeadm upgrade plan
```

### upgrade to the 1.30.1

```sh

sudo kubeadm upgrade apply v1.30.1
```
### Upgrade the kubelet and kubectl

```sh
apt-mark unhold kubelet kubectl && \
apt-get update && apt-get install -y kubelet=1.30.1-1.1 kubectl=1.30.1-1.1 && \
apt-mark hold kubelet kubectl
```



### Restart the kubelet:

```sh
sudo systemctl daemon-reload
sudo systemctl restart kubelet
```

# Upgrading the worker node 

### Drain the worker node

```
k drain node01 --ignore-daemonsets
```
### ssh to the node01

```
ssh node01
```

### uprade the node

```
sudo kubeadm upgrade node
```
### Upgrade the kubelet and kubectl

```sh
apt-mark unhold kubelet kubectl && \
apt-get update && apt-get install -y kubelet=1.30.1-1.1 kubectl=1.30.1-1.1 && \
apt-mark hold kubelet kubectl
```

### Restart the kubelet:

```sh
sudo systemctl daemon-reload
sudo systemctl restart kubelet
```

### uncordon the node 

```
k uncordon node01
```

# Verify the nodes

```
k get nodes
```
