---
title: "確保ELB服務角色<Ensure the ELB Service Role exists>"
date: 2018-09-18T17:40:09-05:00
weight: 29
---

<!---In AWS accounts that have never created a load balancer before, it's possible
that the service role for ELB might not exist yet.--->
在尚未創建過負載平衡的AWS帳號中，ELB角色可能不存在

<!---We can check for the role, and create it if it's missing.

Copy/Paste the following commands into your Cloud9 workspace:--->
確認角色是否存在，如果沒有該角色請建立它

複製/貼上下列Command 到 您的Cloud9 workspace:

```
aws iam get-role --role-name "AWSServiceRoleForElasticLoadBalancing" || aws iam create-service-linked-role --aws-service-name "elasticloadbalancing.amazonaws.com"
```
