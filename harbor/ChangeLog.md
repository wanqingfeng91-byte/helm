# 变更记录：

1. 编辑环境：本地测试环境
2. ingress：ingress-nginx(svc类型NodePort)
3. Harbor的存储用的本地SC
4. Harbor指定`Ingress=Nginx`
5. Harbor指定storageClass=`local-path`

```
kubectl apply -f https://raw.githubusercontent.com/rancher/local-path-provisioner/v0.0.34/deploy/local-path-storage.yaml
```