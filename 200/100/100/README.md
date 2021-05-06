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

- If you're using a managed cloud Kubernetes service which supplies LoadBalancers, then run the following:

```$ arkade install openfaas --load-balancer```

***Note***: the --load-balancer flag has a default of false, so by passing the flag, the installation will request one from your cloud provider.

Or install with helm (advanced).

If you prefer, you can install OpenFaaS using the [helm chart](https://github.com/openfaas/faas-netes/blob/master/chart/openfaas/README.md) instructions.

