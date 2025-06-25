## Name: Service Filter
## Video: [link](https://www.loom.com/share/69cc75ef6c1e4b95a05ac3b4aa341eae?sid=80f5a586-b4de-4037-9bb3-332d12495c6a)
## KillerCoda [link](https://killercoda.com/sachin/course/CKA/service-filter)
## Your svc-filter.sh should look like
```
#!/bin/bash
  
kubectl get service redis-service -o jsonpath='{.spec.ports[0].targetPort}'

```
Check if it is working correctly
```
chmod 777 svc-filter.sh
./svc-filter.sh

```
