# 100 - Install OpenFaaS with arkade

***arkade*** installs OpenFaaS using its official helm chart. It can also offer other software with a user-friendly CLI such as cert-manager and nginx-ingress. It's the easiest and quickest way to get up and running.

## 100 - Get arcade

For MacOS / Linux:

```$ curl -SLsf https://dl.get-arkade.dev/ | sudo sh```

For Windows:

```$ curl -SLsf https://dl.get-arkade.dev/ | sh```

## 200 - Install the OpenFaaS app

- If you're using a local Kubernetes cluster or a VM, then run:

```$ arkade install openfaas```

You will see something like this:

```
Using Kubeconfig: ./k3sconfig
[Warning] unable to create secret basic-auth, may already exist: error: failed to create secret secrets "basic-auth" already exists
Client: x86_64, Linux
2021/05/06 13:46:20 User dir established as: /home/cloud_user/.arkade/
"openfaas" already exists with the same configuration, skipping

Hang tight while we grab the latest from your chart repositories...
...Successfully got an update from the "openfaas" chart repository
Update Complete. ⎈Happy Helming!⎈

VALUES values.yaml
Command: /home/cloud_user/.arkade/bin/helm [upgrade --install openfaas openfaas/openfaas --namespace openfaas --values /tmp/charts/openfaas/values.yaml --set clusterRole=false --set openfaasImagePullPolicy=IfNotPresent --set queueWorker.replicas=1 --set queueWorker.maxInflight=1 --set basic_auth=true --set gateway.directFunctions=false --set operator.create=false --set faasnetes.imagePullPolicy=Always --set basicAuthPlugin.replicas=1 --set gateway.replicas=1 --set ingressOperator.create=false --set serviceType=NodePort]
W0506 13:46:21.446221    7966 loader.go:223] Config not found: ./k3sconfig
W0506 13:46:21.446536    7966 loader.go:223] Config not found: ./k3sconfig
W0506 13:46:21.446594    7966 loader.go:223] Config not found: ./k3sconfig
Error: Kubernetes cluster unreachable: Get "http://localhost:8080/version?timeout=32s": dial tcp [::1]:8080: connect: connection refused
Error: exit code 1, stderr: W0506 13:46:21.446221    7966 loader.go:223] Config not found: ./k3sconfig
W0506 13:46:21.446536    7966 loader.go:223] Config not found: ./k3sconfig
W0506 13:46:21.446594    7966 loader.go:223] Config not found: ./k3sconfig
Error: Kubernetes cluster unreachable: Get "http://localhost:8080/version?timeout=32s": dial tcp [::1]:8080: connect: connection refused
```

- If you're using a managed cloud Kubernetes service which supplies LoadBalancers, then run the following:

```$ arkade install openfaas --load-balancer```

***Note***: the --load-balancer flag has a default of false, so by passing the flag, the installation will request one from your cloud provider.

Or install with helm (advanced).

If you prefer, you can install OpenFaaS using the [helm chart](https://github.com/openfaas/faas-netes/blob/master/chart/openfaas/README.md) instructions.

