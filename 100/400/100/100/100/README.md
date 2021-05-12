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
$ kubectl version
```

If you get below error:

```
Client Version: version.Info{Major:"1", Minor:"21", GitVersion:"v1.21.0", GitCommit:"cb303e613a121a29364f75cc67d3d580833a7479", GitTreeState:"clean", BuildDate:"2021-04-08T16:31:21Z", GoVersion:"go1.16.1", Compiler:"gc", Platform:"linux/amd64"}
The connection to the server localhost:8080 was refused - did you specify the right host or port?
```

Try this: ... more
