# Example of Loki Stack in K8S cluster


## Example

* the kubernetes cluster with configured persistent volumes and ingress-controller
* **kubectl** ([installation guide is here](https://kubernetes.io/docs/tasks/tools/install-kubectl/)), **helm** ([installation guide is here](https://helm.sh/docs/intro/install/))
* example domain **grafana.example.com**


## Namespace

Create the monitoring namespace
```
kubectl create namespace monitoring
```

![created namespace](screenshots/screenshot-namespace.png)


## Loki stack

Add and update Loki helm chart repository
```
helm repo add loki https://grafana.github.io/loki/charts
helm repo update
```

![helm repo](screenshots/screenshot-helm-repo.png)


Install Loki stack
```
helm install loki loki/loki-stack --namespace monitoring -f loki.values.yaml
```

![loki pods](screenshots/screenshot-loki-pods.png)

