---
title: "Cleanup"
date: 2020-07-08T09:36:58-04:00
draft: false
weight: 90
tags:
  - beginner
  - CON203
---

停止proxy並刪除dashboard的部署

```bash
# 把 proxy 殺掉
pkill -f 'kubectl proxy --port=8080'

# 刪除 dashboard
kubectl delete -f https://raw.githubusercontent.com/kubernetes/dashboard/${DASHBOARD_VERSION}/aio/deploy/recommended.yaml

unset DASHBOARD_VERSION
```
