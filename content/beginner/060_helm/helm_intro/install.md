---
title: "透過CLI安裝Helm<Install Helm CLI>"
date: 2018-08-07T08:30:11-07:00
weight: 5
---
<!--## Install the Helm CLI-->
## 透過CLI安裝Helm
<!--Before we can get started configuring Helm, we'll need to first install the
command line tools that you will interact with. To do this, run the following:-->
在開始配置Helm之前, 首先需要安裝 command line 工具，請執行下列命令:

```sh
curl -sSL https://raw.githubusercontent.com/helm/helm/master/scripts/get-helm-3 | bash
```
<!--We can verify the version-->
執行以下命令，確認版本:

```sh
helm version --short
```
<!--Let's configure our first Chart repository. Chart repositories are similar to
APT or yum repositories that you might be familiar with on Linux, or Taps for
Homebrew on macOS.

Download the `stable` repository so we have something to start with:-->
讓我們配置我們的第一個"Chart repository"。 Chart repository類似於在Linux上熟悉的APT或yum repositories，或是macOS的Homebrew。
下載`stable`repository，以便我們從以下內容開始：



```sh
helm repo add stable https://kubernetes-charts.storage.googleapis.com/
```

<!--Once this is installed, we will be able to list the charts you can install:-->
安裝完成後，我們將列出您可以安裝的Charts

```sh
helm search repo stable
```

<!--Finally, let's configure Bash completion for the `helm` command:-->
最後，讓我們配置Bash來完成`helm`指令

```sh
helm completion bash >> ~/.bash_completion
. /etc/profile.d/bash_completion.sh
. ~/.bash_completion
source <(helm completion bash)
```