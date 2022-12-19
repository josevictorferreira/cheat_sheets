
Install and setup minikube.

Add the aws secret to pull images:

```bash
kubectl create secret docker-registry ecr \                                                  
  --docker-server 27327327AWSACCOUNTID.dkr.ecr.sa-east-1.amazonaws.com \
  --docker-username=AWS \
  --docker-password=$(aws ecr get-login-password) -n development
```

Port forward a specific pod port to local machine:

```bash
kubectl port-forward keycloak-0 -n development 8080:8080
```

