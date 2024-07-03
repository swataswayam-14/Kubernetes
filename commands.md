# Kubernetes Commands

This file contains a collection of commonly used Kubernetes commands and their descriptions.

## Cluster Management

- Deletes a single-node Kubernetes cluster created using Kind (Kubernetes in Docker).


kind delete cluster -n local

- Creates a Kubernetes cluster with 2 worker nodes and 1 master node using Kind. The cluster configuration is specified in the clusters.yml file.


kind create cluster --config clusters.yml --name local2


## Node and Pod Management

- Displays information about the nodes in the Kubernetes cluster.


kubectl get nodes

- Displays detailed information about the nodes in the Kubernetes cluster with a verbosity level of 8.

 
kubectl get nodes --v=8

- Lists all the pods in the default namespace.


kubectl get pods

- Watches for changes in the pods and displays updates in real-time.

kubectl get pods -w

- //description

kubectl get pods --all-namespaces

- //description

kubectl get namespaces

- //description

kubectl create namespace backend

- //description

kubectl create namespace frontend


- //description

kubectl get deployment --namespace backend


- //description

kubectl get pods --namespace backend

- Creates a new pod named "nginx" using the "nginx" Docker image and exposes port 80.

 
kubectl run nginx --image=nginx --port=80

- Retrieves the logs for the "nginx" pod.

 
kubectl logs nginx

- Displays detailed information about the "nginx" pod.

 
kubectl describe pod nginx

- Creates a new pod named "postgres" using the "postgres" Docker image and exposes port 5432.


kubectl run postgres --image=postgres --port=5432

- Deletes the "nginx" pod.

 
kubectl delete pod nginx

## Manifest Application


kubectl apply -f manifest.yml

Applies the Kubernetes manifest defined in the manifest.yml file to the cluster.


## Deployment

- Apply a deployment configuration from a YAML file

kubectl apply -f deployment.yml

- List all deployments in the current namespace

kubectl get deployment

- Delete a deployment by name

kubectl delete deployment nginx-deployment

## replicaset

- List all replicasets in the current namespace

kubectl get rs

- Apply a replicaset configuration from a YAML file

kubectl apply -f replica-set.yml

- List all pods with additional information like node name

kubectl get pods -owide

## services

- Apply a service configuration from a YAML file

kubectl apply -f service.yml


-List all services in the current namespace

kubectl get services


- Create a new kind cluster using a configuration file

kind create cluster --config kind.yml --name local
kubectl apply -f deployment.yml
kubectl apply -f service.yml