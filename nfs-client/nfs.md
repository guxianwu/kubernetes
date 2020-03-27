1.安装nfs-utils服务

/etc/exports 中添加共享路径

```
[root@mast  html]# cat /etc/exports
/video/nfs *(rw,no_root_squash)
```

2.修改depoyment.yml中的IP，挂载路径

3.部署

kubectl apply -f .

```
[root@master nfs-client]# kubectl apply -f 
class.yaml       deployment.yaml  rbac.yaml        
[root@master nfs-client]# kubectl apply -f .
```

4.查看

```
[root@master nfs-client]# kubectl get pods |grep nfs
nfs-client-provisioner-cb99f66c5-fh9tj   1/1     Running   0          17m

etcd-2               <unknown>
[root@master nfs-client]# kubectl get sc
NAME                  PROVISIONER      AGE
managed-nfs-storage   fuseim.pri/ifs   18m
```

