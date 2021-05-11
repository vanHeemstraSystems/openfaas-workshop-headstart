# 100 - Install latest kubectl on Linux

Run following commands:

```
$ export VER=$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)
$ curl -LO https://storage.googleapis.com/kubernetes-release/release/$VER/bin/linux/amd64/kubectl
$ chmod +x kubectl
$ sudo mv kubectl /usr/local/bin/
```
