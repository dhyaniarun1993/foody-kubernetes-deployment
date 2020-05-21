# foody-kubernetes-deployment

This repository contains kubernetes deployment config files for foody system.

## Getting Started

These instruction will get you a copy of the foody system up and running on your kubernetes cluster for testing purposes. 

## Prerequisites

You need to have a kuberenetes cluster up and running.

## Deploy service to Kubernetes

Apply the configuration files to the kubernetes cluster.

### Types of service:

#### Common service

Common services includes databases(mysql, mongo etc), caching service(redis), queuing service(kafka) and tracing service(jaeger)

Note:
```sh
1. Staging configuration are not ideal for production usage. They are only meant for development and testing purpose.
2. Pods in the staging configuration are using local disk to store data. All the data stored in the disk will be lost if the pod terminates. To prevent this use persistent volumes.
```

##### Redis
To deploy redis to the kuberntes cluster, use following command

```sh
kubectl apply -f common/redis/stage/
```

##### MySQL
To deploy mysql to the kubernetes cluster, use following command

```sh
kubectl apply -f common/mysql/stage/
```

##### Jaeger
To deploy jaeger to the kubernetes cluster, use following command

```sh
kubectl apply -f common/jaeger/stage/
```

To access jaeger UI, use the following command, then visit http://localhost:80 in browser

```sh
kubectl port-forward service/jaeger-query 80:80
```

## Progress

### Applications

- [ ] account-service
- [ ] customer-management-system
- [ ] rider-management-service
- [ ] merchant-management-system
- [ ] otp-service
- [ ] notification-service
- [ ] catalog-service
- [ ] order-management-system
- [ ] coupon-management-system
- [ ] delivery-management-system

### Common

- [x] mysql
- [x] redis
- [x] jaeger
- [ ] mongo