---
title: "部署我們的範例應用程式<Deploy our Sample Applications>"
date: 2018-09-18T16:01:14-05:00
weight: 5
---

{{< output "linenos=true" >}}
apiVersion: apps/v1
kind: Deployment
metadata:
  name: ecsdemo-nodejs
  labels:
    app: ecsdemo-nodejs
  namespace: default
spec:
  replicas: 1
  selector:
    matchLabels:
      app: ecsdemo-nodejs
  strategy:
    rollingUpdate:
      maxSurge: 25%
      maxUnavailable: 25%
    type: RollingUpdate
  template:
    metadata:
      labels:
        app: ecsdemo-nodejs
    spec:
      containers:
      - image: brentley/ecsdemo-nodejs:latest
        imagePullPolicy: Always
        name: ecsdemo-nodejs
        ports:
        - containerPort: 3000
          protocol: TCP
{{< /output >}}

<!---In the sample file above, we describe the service and  *how* it should be deployed.
We will write this description to the kubernetes api using kubectl, and kubernetes
will ensure our preferences are met as the application is deployed.<br>--->

在上述範例檔案中，描述了服務與如何部署，我們將透過kubectl寫入描述內容到kubenetes api中，並且kubenetes將會確保在部署後，performance滿足應用程式需求<br>

<!---The containers listen on port 3000, and native service discovery will be used
to locate the running containers and communicate with them.<br>--->
容器服務監聽 3000 port，將使用本機服務發現並與正在運行的容器溝通