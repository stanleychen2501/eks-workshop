---
title: "存取Dashboard<Access the Dashboard>"
date: 2018-08-07T08:30:11-07:00
weight: 30
---

現在我們可以存取 Kubernetes Dashboard

1. 在你的Cloud9環境, 點擊 **Tools / Preview / Preview Running Application**
1. 捲動頁面到 **the end of the URL** 並加上:

```text
/api/v1/namespaces/kubernetes-dashboard/services/https:kubernetes-dashboard:/proxy/
```

<!---The Cloud9 Preview browser doesn't appear to support the token authentication, so once you have the login screen in the cloud9 preview browser tab, press the **Pop Out** button to open the login screen in a regular browser tab, like below: <br>--->
Cloud9 Preview預覽器不支援token認證，因此您需在cloud9 Preview預覽器器標籤中打開瀏覽器，請按** Pop Out **按鈕在瀏覽器選項打開登錄畫面，如下所示：
![popout](/images/popout.png)


<!---Open a New Terminal Tab  and enter--->
打開新的Terminal Tab 並按 Enter
```bash
aws eks get-token --cluster-name eksworkshop-eksctl | jq -r '.status.token'
```

<!---Copy the output of this command and then click the radio button next to
*Token* then in the text field below paste the output from the last command.--->

複製此命令的output，然後點擊旁邊的按鈕* Token *，然後在下面的文字區域中貼上前一條命令的output
![Token page](/images/dashboard-connect.png)

<!---Then press *Sign In*.<br>-->
然後點選 *Sign In*