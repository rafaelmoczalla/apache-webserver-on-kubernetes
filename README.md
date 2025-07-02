# Tutorial: Apache Webserver on Kubernetes
Create an example Apache Webserver & deploy the server to a local Kubernetes cluster.

## Prerequisits
1. This project requires Docker Desktop to be installed.
2. Enable a 4 node Kubernetes Cluster in Docker Desktop Settings.

## Quickstart
Check if Kubernetes is running properly.
```bash
kubectl get nodes
```

### Deploy & Start the Apache Webserver
Deploy the Apache Webserver.
```bash
kubectl apply -f apache-deployment.yaml
```
Start the Apache Webserver service.
```bash
kubectl apply -f apache-service.yaml
```
Check if the Apache Webserver service is created.
```bash
kubectl get services
```
Check if the Apache Webserver is running.
```bash
kubectl get pods
```

### Delete Apache Webserver
Get the deployment name.
```bash
kubectl get deployments --all-namespaces
```
Delete the apache-deployement.
```bash
kubectl scale deployment <deployment_name> --replicas=0
```

Get the service name.
```bash
kubectl get services --all-namespaces
```
Delete the apache-service.
```bash
kubectl scale deployment <deployment_name> --replicas=0
```

## License
Full copyright belongs to me Rafael Moczalla.
