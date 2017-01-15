## Simple container creation via unix socket curl
```
curl --unix-socket /var/run/docker.sock -X POST -H "Content-Type: application/json" http://localhost/containers/create -d '{
     "Hostname":"bob",
     "User":"root",
     "Image":"ubuntu",
     "AttachStdin":false,
     "AttachStdout":true,
     "AttachStderr":true,
     "Tty":false,
     "OpenStdin":false,
     "StdinOnce":false,
     "Env":null,
     "Volumes":{},
     "WorkingDir":"",
     "HostConfig": {
        "Memory":0,
        "MemorySwap":0,
        "Privileged": false,
        "Dns":["8.8.8.8"],
        "VolumesFrom":[]
     }
}'
```

Creates but does **not** start an empty `ubuntu` container.

```
docker ps -a
CONTAINER ID   IMAGE    COMMAND       CREATED         STATUS    PORTS   NAMES
9fc82defec94   ubuntu   "/bin/bash"   9 seconds ago   Created           trusting_hoover
```
