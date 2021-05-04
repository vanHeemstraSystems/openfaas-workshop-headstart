# 100 - k3s using k3d

If you have Docker on your computer, then you can use ```k3d``` from Rancher Labs. It installs a lightweight version of Kubernetes called ```k3s``` and runs it within a Docker container, meaning it will work on any computer that has Docker.

## 100 - Install k3d

See [Install k3d](https://github.com/rancher/k3d)

## 200 - Start a cluster

1. ```k3d cluster create CLUSTER_NAME``` to create a new single-node cluster (= 1 container running k3s + 1 loadbalancer container)
2. ```k3d kubeconfig merge CLUSTER_NAME --switch-context``` to update your default kubeconfig and switch the current-context to the new one
3. execute some commands like ```kubectl get pods --all-namespaces``` If you want to delete default cluster ```k3d cluster delete CLUSTER_NAME```
