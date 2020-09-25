---
title: "擴展後端服務<Scale the Backend Services>"
date: 2018-09-18T17:40:09-05:00
weight: 50
---

<!---When we launched our services, we only launched one container of each. We can
confirm this by viewing the running pods:<br>--->
當服務啟動時，每個服務僅啟動一個容器。我們可以通過查看正在運行的pods來確認這一點:
```
kubectl get deployments
```

<!---Now let's scale up the backend services:<br>--->
現在，擴展後端服務:
```
kubectl scale deployment ecsdemo-nodejs --replicas=3
kubectl scale deployment ecsdemo-crystal --replicas=3
```
<!---Confirm by looking at deployments again:<br>--->
透過再次查看部署進行確認:
```
kubectl get deployments
```

<!---Also, check the browser tab where we can see our application running. You should
now see traffic flowing to multiple backend services.<br>--->
另外，從瀏覽器分頁上查看，我們可以看到應用程式正在執行，現在應該可以看到流量流向不同的後端服務