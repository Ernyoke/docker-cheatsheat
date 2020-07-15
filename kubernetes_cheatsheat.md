# Kubernetes cheatsheat

## Version

`kubectl version`

## Create a single pod

`kubectl run <name> --image <docker-image-name>`

## Create a single deployment

`kubectl create deployment <name> --image <docker-image-name>`

## Remove deployment

`kubectl delete deployment <name>`

## List pods

`kubectl get pods`

`kubectl get pods -w` (watch mode)

## Describe pods

`kubectl describe <name>`

## List services

`kubectl get service`

`kubectl get services`

## Get all

`kubectl get all`

## Scale deployment

`kubectl scale deployment/<name> --replicas=5`

## Expose local name/port - create a ClusterIP

`kubectl expose deployment/<name> --port 8888`

## Create a NodePort Service

`kubectl expose deployment/<name> --port 8888 --name <name-np> --type NodePort`

## Create LoadBalancer Service

`kubectl expose deployment/<name> --port 8888 --name <name-lb> --type LoadBalancer`

## Generators

### Create deployment - Dry run

`kubectl create deployment test --image <name> --dry-run`

### Create deployment - Output YAML

`kubectl create deployment test --image <name> --dry-run -o yaml`

### Create job - Output YAML

`kubectl create job <job-name> --image <img-name> --dry-run -o yaml`

## Declarative kubernetes

### Apply

`kubectl apply -f filename.yml`

`kubectl apply -f filename.yml --dry-run`

`kubectl apply -f filename.yml --server-dry-run`

### API Resources

`kubectl api-resources`

### API Versions

`kubectl api-versions`

### Get all keys for each `kind`

`kubectl explain services --recoursive`

`kubectl explain services.spec`

`kubectl explain services.spec.<spec-name>`



