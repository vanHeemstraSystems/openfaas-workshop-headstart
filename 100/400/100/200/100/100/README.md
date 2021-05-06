# 100 - k3s using k3d

If you have Docker on your computer, then you can use ```k3d``` from Rancher Labs. It installs a lightweight version of Kubernetes called ```k3s``` and runs it within a Docker container, meaning it will work on any computer that has Docker.

## 100 - Install k3d and (optional) k3x

### k3d

See [Install k3d](https://github.com/rancher/k3d)

In short:

```
$ curl -s https://raw.githubusercontent.com/rancher/k3d/main/install.sh | bash
```

You will see:

```
Preparing to install k3d into /usr/local/bin
[sudo] password for cloud_user: 
k3d installed into /usr/local/bin/k3d
Run 'k3d --help' to see what you can do with it.
```

Check with:

```
$k3d --help
```

### k3x

(Optionally) install k3x, 
See https://github.com/inercia/k3x


k3x is a graphical user interface for k3d, making it trivial to have your own local Kubernetes cluster(s).

k3x is perfect for:

- having a fresh Kubernetes cluster in a couple of seconds.
- trying new deployments before going in production.
- learning about Kubernetes.

k3x goals are:

- to create/switch-to/destroy Kubernetes clusters easily.
- to drive the most important operations with global keyboard shortcuts.
- to reduce the learning curve of using Kubernetes.

### k3s-dind

***Note***: Here we use k3s-dind (k3s Docker in Docker), which installs k3s inside a Docker container. See [k3s-dind - Headstart](https://github.com/vanHeemstraSystems/k3s-dind-headstart)

Directory structure is as follows (excerpt):

```
[ROOT]
  - containers
  - -- k3s-dind
  - -- -- Dockerfile
  - -- -- sample.docker-compose.yml
```

## 200 - Start a cluster

***Note***: To see the cluster name etc. as we created with k3s-dind, open the file k3sconfig which you created when working on k3s-dind (previous section).

```
$ cd containers/k3s-dind/
$ vi k3sconfig
```

Above you will see: ```CLUSTER_NAME = default```

1. SKIP AS WE ALREADY HAVE CLUSTER 'default': ```k3d cluster create CLUSTER_NAME``` to create a new single-node cluster (= 1 container running k3s + 1 loadbalancer container)
2. SKIP AS WE ALREADY HAVE CLUSTER 'default': ```k3d kubeconfig merge CLUSTER_NAME --switch-context``` to update your default kubeconfig and switch the current-context to the new one
3. execute some commands like ```kubectl get pods --all-namespaces``` 
4. SKIP AS WE ALREADY HAVE CLUSTER 'default': If you want to delete default cluster ```k3d cluster delete CLUSTER_NAME```
