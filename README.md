## Add the Bitnami Helm Repository:

helm repo add bitnami https://charts.bitnami.com/bitnami
helm repo update

## Install the PostgreSQL Chart:

helm install prj3 bitnami/postgresql --set primary.persistence.enabled=false

## Get the PostgreSQL Connection Details:

POSTGRE_SQL=prj3-postgresql
export POSTGRES_PASSWORD=$(kubectl get secret prj3-postgresql -o jsonpath="{.data.postgres-password}" | base64 -d)
kubectl port-forward svc/"$POSTGRESQL" 5432:5432 &

## Create a Dockerfile for the Python Application
analytics/Dockerfile

## Write a Build Pipeline with AWS CodeBuild

buildspec.yml

## Create Kubernetes Service and Deployment
1. List Services
   kubectl get svc
   kubectl describe svc

3. List Pods
   kubectl get pods
   kubectl describe pods
   
4. List Deployments
   kubectl get deployments
   kubectl describe deployment coworking