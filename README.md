## Deploy cloud compiler


Containerising the Flask Application with Docker

```bash
docker build -t cloud-compiler-parcial .
```

Pushing the Docker Image to Docker Hub

```bash
docker tag cloud-compiler-parcial andrescmm/cloud-compiler-parcial
```
Inicia sesión

```bash
docker login
docker push andrescmm/cloud-compiler-parcial
```

Running a Docker Container
```bash
docker run -p 8080:8080 cloud-compiler-parcial
```

Minikube Kubernetes Cluster
```bash
minikube version
minikube start --driver=docker
```

Deploying to the Minikube Kubernetes Cluster
```bash
kubectl version --client
kubectl apply -f deployment.yml
```

Comprobation
```bash
kubectl get deployment
kubectl get service
```

Getting the Pods
```bash
kubectl get pods
kubectl get pods --all-namespaces
```

The Minikube Deployment Dashboard
```bash
minikube dashboard
minikube service cloud-compiler-parcial-service
```

```bash
kubectl delete deployment --namespace=default --all
kubectl scale deployment cloud-compiler-parcial --replicas=0
kubectl delete pod cloud-compiler-parcial-dcc6f77f9-k2tsx
```
Stop the cluster
```bash
minikube stop --all
```
