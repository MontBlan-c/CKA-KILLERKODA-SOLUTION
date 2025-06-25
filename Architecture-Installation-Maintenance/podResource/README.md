## Video: [link](https://www.loom.com/share/11975e20d4584f8386d7396633cdb332?sid=0b6b5bef-1399-451c-ac16-4f4a4f068226)
## KillerCoda: [link](https://killercoda.com/sachin/course/CKA/pod-resource)
## Name: Pod Resource
# Run the below command

```
a=$(k top pod -A --no-headers | sort -k3 -h -r | head -n1 | awk '{print $2}')

```

```
b=$(k top pod -A --no-headers | sort -k3 -h -r | head -n1 | awk 'print $1')
```


```
echo "$a,$b" > high_cpu_pod.txt
