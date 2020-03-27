 



应用：

```
kubectl apply -f prometheus-rbac.yaml 

kubectl apply -f prometheus-configmap.yaml 

kubectl apply -f prometheus-rules.yaml              

kubectl apply -f prometheus-service.yaml           

kubectl apply -f prometheus-statefulset.yaml 
```

查看：

```
kubectl get pods -n kube-system
kubectl  get pods,svc -n kube-system
```





