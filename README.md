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


### Generate secret for sensitive information

Please update the values below and run. 

```
if [ ! -d secret ]; then
    mkdir secret;
fi;

echo 'USERNAME' > secret/spring.datasource.username
echo 'PASWORD' > secret/spring.datasource.password
echo 'jdbc:mysql://chhs-mysql:3306/DBNAME?characterEncoding=UTF-8' > secret/spring.datasource.url
echo 'mysql.root.password' > secret/mysql.root.password

kubectl create secret generic chhs --from-file=secret
```

# chhs-kubernetes
