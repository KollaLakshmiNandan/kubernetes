apiVersion: apps/v1
kind: ReplicaSet
metadata:
  name: nginx-rs
spec:
  replicas: 3
  selector:
    matchLabels:
      app: nginx-rs
  template:
    metadata:
      labels:
        app: nginx-rs
    spec:
      containers:
      - name: nginx
        image: nginx
## Create ReplicaSet
kubectl apply -f replicasets/nginx-rs.yaml
## Verify
kubectl get pods
## Delete a Pod
kubectl delete pod nginx-rs-xm2vm
## Watch Recreation
kubectl get pods -w
## Result
Deleted Pod:
nginx-rs-xm2vm
Automatically Created Pod:
nginx-rs-crnsc
## Conclusion
ReplicaSet automatically recreated the deleted Pod and maintained the desired state.
## Real World Example
If an application server crashes in production, Kubernetes automatically starts a replacement Pod without manual intervention.