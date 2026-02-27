```
# 部署
helm install webserver-test webserver-chart/ -f webserver-chart/values_test.yaml --create-namespace -n test
helm install webserver-dev  webserver-chart/ -f webserver-chart/values_dev.yaml  --create-namespace -n dev  --set deployment.replicas=2
helm install webserver-prod webserver-chart/ -f webserver-chart/values_prod.yaml --create-namespace -n prod --set deployment.replicas=3

# 升级
helm upgrade -n test webserver-test webserver-chart/ --set deployment.tag=webserverv2
helm upgrade -n dev webserver-dev   webserver-chart/ --set deployment.tag=webserverv2
helm upgrade -n prod webserver-prod webserver-chart/ --set deployment.tag=webserverv2

# 回滚
helm rollback -n test webserver-test
helm rollback -n dev  webserver-dev
helm rollback -n prod webserver-prod
```

