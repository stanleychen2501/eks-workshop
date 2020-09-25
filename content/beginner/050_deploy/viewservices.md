---
title: "尋找Service Address <Find the Service Address>"
date: 2018-09-18T17:40:09-05:00
weight: 40
---

<!--Now that we have a running service that is `type: LoadBalancer` we need to find
the ELB's address.  We can do this by using the `get services` operation of kubectl:-->
現在，我們有一個正在運行的服務是`type: LoadBalancer`我們需要找到ELB Address。我們可以通過kubectl的 "get services "操作來實現

```
kubectl get service ecsdemo-frontend
```

<!--Notice the field isn't wide enough to show the FQDN of the ELB. We can adjust the
output format with this command:-->
我們注意到字段不夠寬，無法显示ELB的FQDN，可以通过此命令来调整输出格式。
```
kubectl get service ecsdemo-frontend -o wide
```

<!--If we wanted to use the data programatically, we can also output via json. This is
an example of how we might be able to make use of json output:-->
如果我們想在程序上使用這些數據，我們也可以通過json輸出<br>
這是一個如何使用json輸出的例子
```
ELB=$(kubectl get service ecsdemo-frontend -o json | jq -r '.status.loadBalancer.ingress[].hostname')

curl -m3 -v $ELB
```
<!--{{% notice tip %}}
It will take several minutes for the ELB to become healthy and start passing traffic to the frontend pods.
{{% /notice %}}

You should also be able to copy/paste the loadBalancer hostname into your browser and see the application running.
Keep this tab open while we scale the services up on the next page.-->

{{% notice 小秘訣 %}}
這需要花幾分鐘時間去讓ELB服務正常，並且開始傳送流量到前端pods
{{% /notice %}}

您應該也可以複製/貼上 負載均衡hostname 到您的瀏覽器，並且看到應用程式正在執行<br>
在下一頁擴展服務時，請保持此分頁開啟