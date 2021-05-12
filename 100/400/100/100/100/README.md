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

Try this: ... more
