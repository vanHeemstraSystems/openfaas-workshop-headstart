# 100 - Install latest kubectl on Linux

Run following commands:

```
$ export VER=$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)
```

```
$ curl -LO https://storage.googleapis.com/kubernetes-release/release/$VER/bin/linux/amd64/kubectl
```

```
$ chmod +x kubectl
```

```
$ sudo mv kubectl /usr/local/bin/
```

Check the result:

```
$ kubectl version -o json
```

If you get below error:

```
{
  "clientVersion": {
    "major": "1",
    "minor": "21",
    "gitVersion": "v1.21.0",
    "gitCommit": "cb303e613a121a29364f75cc67d3d580833a7479",
    "gitTreeState": "clean",
    "buildDate": "2021-04-08T16:31:21Z",
    "goVersion": "go1.16.1",
    "compiler": "gc",
    "platform": "linux/amd64"
  }
}
The connection to the server localhost:8080 was refused - did you specify the right host or port?
```

Then try this: Check that the api server is actually running and hasn’t crashed:
```
$ docker ps | grep kube-apiserver
$
```

This means the kube-apiserver is not running.

Don't worry, this is because here in the instructions we have ***not yet*** ran ```k3s-dind docker-compose up -d```. Once done and started as follows, kube-apiserver will be running:

```
$ cd containers/k3s-dind/
$ docker-compose up -d
$ docker ps
CONTAINER ID   IMAGE               COMMAND                  CREATED          STATUS         PORTS                                                                                                 NAMES
7d70ac00d532   k3s-dind_k3s-dind   "/usr/local/bin/star…"   10 seconds ago   Up 7 seconds   0.0.0.0:8080->8080/tcp, :::8080->8080/tcp, 2375-2376/tcp, 0.0.0.0:8443->8443/tcp, :::8443->8443/tcp   k3s
```


