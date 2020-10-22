---
title: "建立Chart Create a Chart"
date: 2018-08-07T08:30:11-07:00
weight: 10
---

<!--Helm charts have a structure similar to:-->
Helm chart 的架構類似於：

<!--{{< output >}}
/eksdemo
  /Chart.yaml  # a description of the chart
  /values.yaml # defaults, may be overridden during install or upgrade
  /charts/ # May contain subcharts
  /templates/ # the template files themselves
  ...
{{< /output >}}-->

{{< output >}}
/eksdemo
  /Chart.yaml  # Chart 說明
  /values.yaml # 預設, 在安裝或升級過程中可能被覆蓋
  /charts/ # 可能包含 subcharts
  /templates/ # 範例文件
  ...
{{< /output >}}

我們將會根據這個範例，用下列命令來新增新的名為 **eksdemo** 的 Chart 
<!--We'll follow this template, and create a new chart called **eksdemo** with the following commands:-->

```sh
cd ~/environment
helm create eksdemo
```
