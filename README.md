# accounts-service
This service is a spring boot application responsible for creating and managing bank accounts.


docker build -t accounts-service:1
kubectl create deployment accounts-service --image=accounts-service:1 --dry-run=client -o=yaml > deployment.yaml
echo --- >> deployment.yaml
kubectl create service clusterip accounts-service --tcp=8080:8080 --dry-run=client -o=yaml >> deployment.yaml
kubectl apply -f deployment.yaml
kubectl get all

kubectl port-forward svc/account-service 8080:8080

