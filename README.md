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

Forward the Apache Webserver to your local host & check if you can load the website.
```bash
kubectl port-forward svc/apache-service 8080:80
curl http://localhost:8080
```

### Delete Apache Webserver
Get the deployment name.
```bash
kubectl get deployments --all-namespaces
```
Delete the apache-deployement.
```bash
kubectl scale deployment apache-deployment --replicas=0
```

Get the service name.
```bash
kubectl get services --all-namespaces
```
Delete the apache-service.
```bash
kubectl delete service apache-service
```

## License
Full copyright belongs to me Rafael Moczalla.
