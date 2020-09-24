---
title: "部署官方Kubernetes Dashboard<Deploy the Official Kubernetes Dashboard>"
date: 2018-08-07T08:30:11-07:00
weight: 10
---

The official Kubernetes dashboard is not deployed by default, but there are
instructions in [the official documentation](https://kubernetes.io/docs/tasks/access-application-cluster/web-ui-dashboard/)<br>
官方的Kubernetes dashboard預設沒有部署，但是在[官方文件](https://kubernetes.io/docs/tasks/access-application-cluster/web-ui-dashboard/)中有介紹

We can deploy the dashboard with the following command:<br>
我們可以根據以下Command部署Dashboard:
```bash
export DASHBOARD_VERSION="v2.0.0"

kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/${DASHBOARD_VERSION}/aio/deploy/recommended.yaml
```

Since this is deployed to our private cluster, we need to access it via a proxy.
`kube-proxy` is available to proxy our requests to the dashboard service.  In your
workspace, run the following command:<br>
由於這已部署到我們私有的cluster，我們需要透過proxy來存取。
`kube-proxy` 可以將我們的請求發送到Dashboard 服務中，在您的workspace中，run以下command:

```bash
kubectl proxy --port=8080 --address=0.0.0.0 --disable-filter=true &
```

This will start the proxy, listen on port 8080, listen on all interfaces, and
will disable the filtering of non-localhost requests.
這會啟動proxy並且listen 8080 port與所有接口以及禁用過濾非本機的請求

This command will continue to run in the background of the current terminal's session.<br>
這Command 將會在目前的terminal背景運行

{{% notice warning %}}
We are disabling request filtering, a security feature that guards against XSRF attacks.<br>
This isn't recommended for a production environment, but is useful for our dev environment.<br>
我們正禁用請求過濾，該功能可以防禦 XSRF 攻擊<br>
不建議在生產環境中使用它，但可用於開發環境
{{% /notice %}}
