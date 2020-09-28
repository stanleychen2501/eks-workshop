---
title: "Helm"
chapter: true
weight: 60
pre: '<i class="fa fa-film" aria-hidden="true"></i> '
tags:
  - beginner
  - CON203
  - CON205
  - CON206
---

# Helm

{{< youtube XIVCS2j_JxU >}}

<!--{{% notice info %}}
This tutorial has been updated for Helm v3. In version 3, the Tiller component
was removed, which simplified operations and improved security.
{{% /notice %}}-->

{{% notice info %}}
本教學已經針對Helm更新至版本3，在版本3中,為了提生安全性並簡化操作"Tiller component"已經被移除。
{{% /notice %}}

<!--{{% notice note %}}
If you need to migrate from Helm v2 to v3 [click here for the official documentation](https://helm.sh/blog/migrate-from-helm-v2-to-helm-v3/).
{{% /notice %}}-->

{{% notice note %}}
如果您需要將Helm v2 遷移到 v3 [請點擊官方文件](https://helm.sh/blog/migrate-from-helm-v2-to-helm-v3/).
{{% /notice %}}

<!--[Helm](https://helm.sh/) is a package manager for Kubernetes that packages
multiple Kubernetes resources into a single logical deployment unit called
a **Chart**. Charts are easy to create, version, share, and publish.

In this chapter, we'll cover [installing Helm](helm_intro).  Once installed,
we'll demonstrate how Helm can be used to [deploy a simple nginx
webserver](helm_nginx), and a more [sophisticated microservice](helm_micro).

![Helm Logo](/images/helm-logo.svg)-->
[Helm](https://helm.sh/) 是Kubernetes的管理工具之一 用於打包多個Kubenetes 資源整合到 **Chart**。Charts 創建容易，包含版本控制共、享和發布。

此章節, 我們將介紹如何[安裝 Helm](helm_intro).  安裝完成後,
我們將展示如何使用Helm來 [部署簡單Nginx webserver](helm_nginx), 和更多 [成熟的微服務](helm_micro).

![Helm Logo](/images/helm-logo.svg)