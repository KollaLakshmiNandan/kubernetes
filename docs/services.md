apiVersion: v1
kind: Service
metadata:
  name: nginx-service
spec:
  selector:
    app: nginx
  ports:
  - protocol: TCP
    port: 80
    targetPort: 80
  type: NodePort
## Apply
kubectl apply -f services/nginx-service.yaml
## Verify
kubectl get services
## Result
NodePort exposes application outside cluster.
## Real World
Users access websites through services.