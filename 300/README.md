# 300 - Log into your OpenFaaS gateway

## 100 - Check the gateway is ready

```$ kubectl rollout status -n openfaas deploy/gateway```

You may see this:

```Error from server (NotFound): deployments.apps "gateway" not found```

- If you're using your laptop, a VM, or any other kind of Kubernetes distribution run the following instead:

```$ kubectl port-forward svc/gateway -n openfaas 8080:8080```

This command will open a tunnel from your Kubernetes cluster to your local computer so that you can access the OpenFaaS gateway. There are other ways to access OpenFaaS, but that is beyond the scope of this workshop.

Your gateway URL is: ```http://127.0.0.1:8080```

- If you're using a managed cloud Kubernetes service then get the LoadBalancer's IP address or DNS entry from the ```EXTERNAL-IP``` field from the command below.

```$ kubectl get svc -o wide gateway-external -n openfaas```

Your URL will be the IP or DNS entry above on port ```8080```.

## 200 - Log in

```
export OPENFAAS_URL="" # Populate as above

# This command retrieves your password
PASSWORD=$(kubectl get secret -n openfaas basic-auth -o jsonpath="{.data.basic-auth-password}" | base64 --decode; echo)

# This command logs in and saves a file to ~/.openfaas/config.yml
echo -n $PASSWORD | faas-cli login --username admin --password-stdin
```

## 300 - Check that faas-cli list works

```$ faas-cli list```
