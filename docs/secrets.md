## Create Secret
kubectl create secret generic db-secret \
--from-literal=password=nandy123
## Verify
kubectl get secrets
kubectl describe secret db-secret
## Secret YAML
apiVersion: v1
kind: Secret
metadata:
  name: db-secret
type: Opaque
data:
  password: bmFuZHkxMjM=
## Result
Sensitive data stored securely.
## Real World
Database passwords, API keys and tokens.