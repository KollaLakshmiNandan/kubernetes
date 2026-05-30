apiVersion: apps/v1
kind: ReplicaSet
metadata:
  name: nginx-rs
spec:
  replicas: 3
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
## Apply
kubectl apply -f replicasets/nginx-rs.yaml
## Verify
kubectl get rs
kubectl get pods
## Result
ReplicaSet ensures required number of pods are running.
## Real World
Maintains application availability.