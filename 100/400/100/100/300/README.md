# 300 - Install latest kubectl on Windows

Run following commands:

```
$ export VER=$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)
$ curl -LO https://storage.googleapis.com/kubernetes-release/release/$VER/bin/windows/amd64/kubectl.exe
$ chmod +x kubectl.exe
$ mkdir -p $HOME/bin/
$ mv kubectl $HOME/bin/
```
