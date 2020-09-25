---
title: "部署前端服務<Deploy Frontend Service>"
date: 2018-09-18T17:40:09-05:00
weight: 30
---

<!--#### Challenge:
**Let’s bring up the Ruby Frontend!**<br>-->
#### 挑戰:
**把Ruby前端帶起來**

<!--{{%expand "Expand here to see the solution" %}}
{{% /expand %}}
-->

{{%expand "展開解決方案" %}}
<!---Copy/Paste the following commands into your Cloud9 workspace:<br>--->
複製/貼上下列Command 到 您的Cloud9 workspace:

```
cd ~/environment/ecsdemo-frontend
kubectl apply -f kubernetes/deployment.yaml
kubectl apply -f kubernetes/service.yaml
```

<!---We can watch the progress by looking at the deployment status:<br>--->
我們可以透過查看部署狀態來觀察目前進度

```
kubectl get deployment ecsdemo-frontend
```
{{% /expand %}}
