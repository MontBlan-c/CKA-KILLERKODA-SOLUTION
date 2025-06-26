### Group: Architecture, Installation & Maintenance
### Name: Log Reader - 2
### Weight: 4
### KillerCoda: [link](https://killercoda.com/sachin/course/CKA/log-reader-1)
### Video: [link](https://www.loom.com/share/9aa809f5e13c46718d481b059d8fda96)
### YouTube: [link](https://youtu.be/Snx5sOAgg_E)
### Task: 
alpine-reader-pod pod is running, save All INFO and ERROR's pod logs in podlogs.txt
## Run the below command (Full Solution)

```
k logs alpine-reader-pod > podlogs.txt
```
## Step by Step Solution:
### Resources: [link](https://kubernetes.io/docs/reference/kubectl/generated/kubectl_logs/)
1. ## Check Pods
   ```
   kubectl get pods
   ```
   We see: <br>
   `NAME                READY   STATUS    RESTARTS   AGE` <br>
   `alpine-reader-pod   1/1     Running   0          99s` <br>
3. ## Check Logs
   We can grab the command from docs: <br> `kubectl logs [-f] [-p] (POD | TYPE/NAME) [-c CONTAINER] ` <br>
   
   So we don't need `-f` or `-p` <br> `kubectl logs (POD | TYPE/NAME) [-c CONTAINER] ` <br>
   
   Its a pod so we can wright the name of the pod<br> `kubectl logs alpine-reader-pod [-c CONTAINER] ` <br>
   
   We can see above that it only has one container. <br>
   ```
   kubectl logs alpine-reader-pod
   ```
   The results might look like: <br>
  ` ERROR: Mon Oct 1 10:30:23 UTC 2023 Log in Error!` <br>
`INFO: Mon Oct 1 10:30:23 UTC 2023 Logged In` <br>
`ERROR: Mon Oct 1 10:30:23 UTC 2023  Log in Error!` <br>
`INFO: Mon Oct 1 10:30:23 UTC 2023 Logged In` <br>
`ERROR: Mon Oct 1 10:30:23 UTC 2023  Log in Error!` <br>
`INFO: Mon Oct 1 10:30:23 UTC 2023 Logged In` <br>
`ERROR: Mon Oct 1 10:30:23 UTC 2023  Log in Error!` <br>
`INFO: Mon Oct 1 10:30:23 UTC 2023 Logged In` <br>
`ERROR: Mon Oct 1 10:30:23 UTC 2023  Log in Error!` <br>
5. ## File it
   We need to put this into the file `podlogs.txt ` <br>
   We can either create the file (``` vim podlogs.txt ```) and paste the logs into it or, do it in one command:
   ```
   kubectl logs alpine-reader-pod > podlogs.txt
   ```
7. ## Check File
    We can check this file with:
   ```
   cat podlogs.txt
   ```
   We should see: <br>
   `ERROR: Mon Oct 1 10:30:23 UTC 2023 Log in Error!` <br>
`INFO: Mon Oct 1 10:30:23 UTC 2023 Logged In ` <br>
`ERROR: Mon Oct 1 10:30:23 UTC 2023  Log in Error!` <br>
`INFO: Mon Oct 1 10:30:23 UTC 2023 Logged In` <br>
`ERROR: Mon Oct 1 10:30:23 UTC 2023  Log in Error!` <br>
`INFO: Mon Oct 1 10:30:23 UTC 2023 Logged In` <br>
`ERROR: Mon Oct 1 10:30:23 UTC 2023  Log in Error!` <br>
`INFO: Mon Oct 1 10:30:23 UTC 2023 Logged In` <br>
`ERROR: Mon Oct 1 10:30:23 UTC 2023  Log in Error!` <br>
## Done!
