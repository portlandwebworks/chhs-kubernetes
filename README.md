# cchs-kubernetes-demo 



Kubernetes is an open-source system for automating deployment, scaling, and management of containerized applications.

## Advantages
- High Availability
- Auto Scaling
- Docker based containers 
- Platform Independent 
- Open Source


## Limitations
- A robust database tier is more difficult to implement with Kubernetes.  
- AWS RDS Multi-AZ for database tier provides better redundency and automated failover and is recommened for production deployments.
- Kubernetes is not compatible with Amazon's EC2 Container Service. However, the underlying docker container architecture is fully supported. 



### Quickstart
```
gcloud config set project GCE_PROJECT_ID
gcloud config set compute/zone us-central1-c
gcloud container clusters create GCE_PROJECT_ID

kubectl create secret generic chhs --from-literal=spring.datasource.username=USERNAME --from-literal=spring.datasource.password=PASSWORD --from-literal=spring.datasource.url=jdbc:mysql://DB_HOSTNAME:3306/DB_NAME

kubectl create -f frontend-controller.yml
kubectl create -f backend-controller.yml
kubectl create -f frontend-service.yml
kubectl create -f backend-service.yml
```
