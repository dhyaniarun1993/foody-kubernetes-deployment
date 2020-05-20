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
2. Pods in the configuration are using local disk. All the data stored in the disk will be lost if pod terminates. To prevent this use [persistent volumes] (https://kubernetes.io/docs/concepts/storage/persistent-volumes/).
```
To deploy redis to the kuberntes cluster, use following command

```sh
kubectl apply -f common/redis/stage/
```

To deploy mysql to the kubernetes cluster, use following command

```sh
kubectl apply -f common/mysql/stage/
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

- [ ] mysql
- [ ] redis
- [ ] mongo