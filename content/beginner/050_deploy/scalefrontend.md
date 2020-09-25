---
title: "擴展前端<Scale the Frontend>"
date: 2018-09-18T17:40:09-05:00
weight: 60
---

<!---#### Challenge:
**Let's also scale our frontend service!**--->
### 挑戰:<br>
**讓我們也擴展前端服務**

<!--- {{%expand "Expand here to see the solution" %}}
{{% /expand %}}
--->
{{%expand "展開解決方案" %}}
```
kubectl get deployments
kubectl scale deployment ecsdemo-frontend --replicas=3
kubectl get deployments
```
{{% /expand %}}

<!---Check the browser tab where we can see our application running. You should
now see traffic flowing to multiple frontend services.<br>--->
從瀏覽器分頁查看，我們可以看到應用程式正在執行，現在應該可以看到流量流向不同的前端服務