# accounts-service
This service is a spring boot application responsible for creating and managing bank accounts.

### Commands
```
docker build -t accounts-service
kubectl create deployment accounts-service --image=accounts-service --dry-run=client -o=yaml > deployment.yml
echo --- >> deployment.yml
kubectl create service clusterip accounts-service --tcp=8082:8082 --dry-run=client -o=yaml >> deployment.yml
kubectl apply -f deployment.yml
kubectl get all

kubectl port-forward svc/account-service 8082:8082
```

