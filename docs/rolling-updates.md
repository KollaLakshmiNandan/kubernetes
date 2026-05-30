apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-deployment
spec:
  replicas: 5
  selector:
    matchLabels:
      app: nginx
  template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
      - name: nginx
        image: nginx:1.25
## Update Deployment
Change:
image: nginx
To:
image: nginx:1.25
## Apply Changes
kubectl apply -f deployments/nginx-deployment.yaml
## Check Rollout Status
kubectl rollout status deployment/nginx-deployment
## Verify Updated Image
kubectl describe deployment nginx-deploymen
## Monitor Pods
kubectl get pods -w
## What Happens Internally
Old Pod Running
New Pod Created
Health Check Succes
Old Pod Deleted
Repeat Until All Pods Updated
## Result
Kubernetes updates Pods one by one without affecting application availability.
## Real World Example
Netflix, Amazon, and Facebook deploy new application versions using rolling updates to avoid downtime for users.
## Kubernetes Concept Learned
* Deployment
* Rolling Updates
* Zero Downtime Deployment
* Application Version Upgrade
