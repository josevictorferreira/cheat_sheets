# Kubernetes Cheat Sheet

## Kubectl

### Context

List contexts:
```bash
kubectl config get-contexts
```

Current context:
```bash
kubectl config current-context
```

Change current context:
```bash
kubectl config use-context my-cluster-name
```

See the memory and CPU of the pod
```bash
kubectl top pod booster-georef-measures-service-78b6dcb6df-snzzg -n staging
```

### Namespaces

View all namespaces:
```bash
kubectl get namespace
```

Set default namespace:
```bash
kubectl config set-context --current --namespace=<insert-namespace-name-here>
```

## Helm

Helm Install and upgrade:
```bash
helm upgrade --install keycloak codecentric/keycloak -n production --values .helm/custom.yaml
```

Delete a helm:
```bash
helm delete my-release
```

List all persistent volumes:
```bash
kubectl get pv
````