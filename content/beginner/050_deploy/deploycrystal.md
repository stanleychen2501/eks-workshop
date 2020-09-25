---
title: "部署Crystal Backend API<Deployed Crystal Backend API>"
date: 2018-09-18T17:40:03-05:00
weight: 20
---

<!---Let’s bring up the Crystal Backend API!<br>--->
將Crystal Backend API服務帶起來

<!---Copy/Paste the following commands into your Cloud9 workspace:<br>--->
複製/貼上下列Command 到 您的Cloud9 workspace:
```
cd ~/environment/ecsdemo-crystal
kubectl apply -f kubernetes/deployment.yaml
kubectl apply -f kubernetes/service.yaml
```

<!---We can watch the progress by looking at the deployment status:<br>--->
我們可以透過查看部署狀態來觀察目前進度
```
kubectl get deployment ecsdemo-crystal
```
