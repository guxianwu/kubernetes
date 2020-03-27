# metrics-server
kube-apiserver配置文件中添加

```
--requestheader-client-ca-file=/opt/kubernetes/ssl/ca.pem \
--proxy-client-cert-file=/opt/kubernetes/ssl/server.pem \
--proxy-client-key-file=/opt/kubernetes/ssl/server-key.pem \
--requestheader-allowed-names=kubernetes \
--requestheader-extra-headers-prefix=X-Remote-Extra- \
--requestheader-group-headers=X-Remote-Group \
--requestheader-username-headers=X-Remote-User \
--enable-aggregator-routing=true \
```

重启apiserver

```
systemctl restart kube-apiserver
```

应用yaml

```
kubectl create -f .
```

查看是否聚合

```
kubectl get apiservice
-->
v1beta1.metrics.k8s.io                 kube-system/metrics-server   True        86m
```

判断api是否可用

```
kubectl get --raw /apis/metrics.k8s.io/v1beta1/nodes

kubectl top node

kubectl top pod
```





