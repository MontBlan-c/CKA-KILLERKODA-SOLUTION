## KillerCoda: [link](https://killercoda.com/sachin/course/CKA/secret-1)
## Video:[link](https://www.loom.com/share/3c68e6e51b9e496bba30c27747c0afd6?sid=c427084a-2497-4127-a3bd-b8ccba85a71b)
## Run the below command

Edit THE SECRET FILE TO VIEW ENCODED CODE
```
kubectl edit secret database-data -n database-ns

```

COPY DB_PASSWORD AND REPLACE IT WITH <ADD_DB_PASSWORD>
```
echo "<ADD_DB_PASSWORD>" | base64 -d > decoded.txt

```
