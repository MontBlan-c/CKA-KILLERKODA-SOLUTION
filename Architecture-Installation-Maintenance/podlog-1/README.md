## KillerCoda: [link](https://killercoda.com/sachin/course/CKA/pod-log-1)
## Video: [link](https://www.loom.com/share/d8ef7dddbbff41fc844b874e250e86df)
## Name: Pod Log 1
# first store the manifest of the product pod in `pod.yaml`

```
k get pod product -o yaml > pod.yaml

```

### Update the pod manifest in command section 

```
spec:
  containers:
  - command:
    - sh
    - -c
    - echo 'Sony Tv Is Good' && sleep 3600
```    
