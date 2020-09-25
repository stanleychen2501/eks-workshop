---
title: 檢查服務類型<Let's check Service Types>"
date: 2018-09-18T17:40:09-05:00
weight: 25
---

<!--Before we bring up the frontend service, let's take a look at the service types
we are using:
This is `kubernetes/service.yaml` for our frontend service:-->
在啟用前端服務前，讓我們看一下現在運行的服務類型:
這是前端服務的`kubernetes/service.yaml` :
{{< output >}}
apiVersion: v1
kind: Service
metadata:
  name: ecsdemo-frontend
spec:
  selector:
    app: ecsdemo-frontend
  type: LoadBalancer
  ports:
   -  protocol: TCP
      port: 80
      targetPort: 3000
{{< /output >}}

<!--Notice `type: LoadBalancer`: This will configure an ELB to handle incoming traffic
to this service.

Compare this to `kubernetes/service.yaml` for one of our backend services:-->
注意 `type: LoadBalancer`: 將會配置ELB去處理進來的流量到這服務

比較一下後端服務的`kubernetes/service.yaml`
{{< output >}}
apiVersion: v1
kind: Service
metadata:
  name: ecsdemo-nodejs
spec:
  selector:
    app: ecsdemo-nodejs
  ports:
   -  protocol: TCP
      port: 80
      targetPort: 3000
{{< /output >}}

<!--Notice there is no specific service type described. When we check [the kubernetes documentation](https://kubernetes.io/docs/concepts/services-networking/service/#publishing-services-service-types)
we find that the default type is `ClusterIP`. This Exposes the service on a cluster-internal IP.
Choosing this value makes the service only reachable from within the cluster.-->

注意，這沒有描述具體的服務類型<br>

當我們查看[kubernetes文件](https://kubernetes.io/docs/concepts/services-networking/service/#publishing-services-service-types)，我們發現默認類型是`ClusterIP`，這將會把服務暴露在 Cluster 的內部IP上
