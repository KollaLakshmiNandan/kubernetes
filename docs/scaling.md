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
        image: nginx
        ports:
        - containerPort: 80

## Apply
kubectl apply -f deployments/nginx-deployment.yaml
## Verify
kubectl get deployments
kubectl get pods
## Result
Pods increased from 4 to 6.
## Real World
Amazon increases server capacity during sale events.