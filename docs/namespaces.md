kubectl create namespace dev
kubectl create namespace test
kubectl create namespace prod
## Verify
kubectl get namespaces
## Deploy
kubectl apply -f deployments/nginx-deployment.yaml -n dev
## Verify
kubectl get pods -n dev
## Result
Resources isolated by environment.
## Real World
Development, Testing and Production environments.