# serverless-jupyter-notebook 帮助

<p align="center" class="flex justify-center">
    <a href="https://www.serverless-devs.com" class="ml-1">
    <img src="https://editor.devsapp.cn/icon?package=serverless-jupyter-notebook&type=packageType">
  </a>
  <a href="https://www.devsapp.cn/details.html?name=serverless-jupyter-notebook" class="ml-1">
    <img src="https://editor.devsapp.cn/icon?package=serverless-jupyter-notebook&type=packageVersion">
  </a>
  <a href="https://www.devsapp.cn/details.html?name=serverless-jupyter-notebook" class="ml-1">
    <img src="https://editor.devsapp.cn/icon?package=serverless-jupyter-notebook&type=packageDownload">
  </a>
</p>

<description>

快速部署一个 jupyter notebook 到阿里云函数计算

</description>

<table>

## 前期准备
使用该项目，推荐您拥有以下的产品权限 / 策略：

| 服务/业务 | 函数计算 |     
| --- |  --- |   
| 权限/策略 | AliyunFCFullAccess<br/>AliyunContainerRegistryFullAccess |  

</table>

<codepre id="codepre">

# 代码 & 预览

- [ :smiley_cat:  源代码](https://github.com/zjy2414/serverless-jupyter-notebook)
- [:rocket: 预览](http://jupyter-notebook.jupyter-service.1451800943597498.cn-hangzhou.fc.devsapp.net/)

</codepre>

<deploy>

## 部署 & 体验

<appcenter>

-  :fire:  通过 [Serverless 应用中心](https://fcnext.console.aliyun.com/applications/create?serverless-jupyter-notebook) ，
[![Deploy with Severless Devs](https://img.alicdn.com/imgextra/i1/O1CN01w5RFbX1v45s8TIXPz_!!6000000006118-55-tps-95-28.svg)](https://fcnext.console.aliyun.com/applications/create?template=serverless-jupyter-notebook) 该应用。 

</appcenter>

- 通过 [Serverless Devs Cli](https://www.serverless-devs.com/serverless-devs/install) 进行部署：
    - [安装 Serverless Devs Cli 开发者工具](https://www.serverless-devs.com/serverless-devs/install) ，并进行[授权信息配置](https://www.serverless-devs.com/fc/config) ；
    - 初始化项目：`s init serverless-jupyter-notebook -d serverless-jupyter-notebook`   
    - 进入项目，并进行项目部署：`cd serverless-jupyter-notebook && s deploy -y`

</deploy>

<appdetail id="flushContent">

# 应用详情

Jupyter Notebook是基于网页的用于交互计算的应用程序，用户可以在网页中直接编写代码和运行代码，代码的运行结果也会直接在代码块下显示。本应用旨在提供一种在 serverless 架构上运行 Jupyter Notebook 的方法。

注意：首次启动可能需要等待较长时间

## 运行截图

<img src="https://7463-tcb-nkd87viq9wheg653bca0d-a8621b-1304207482.tcb.qcloud.la/Serverless-Jupyter/img1.png" alt="home">

<img src="https://7463-tcb-nkd87viq9wheg653bca0d-a8621b-1304207482.tcb.qcloud.la/Serverless-Jupyter/img2.png" alt="matplot">

<img src="https://7463-tcb-nkd87viq9wheg653bca0d-a8621b-1304207482.tcb.qcloud.la/Serverless-Jupyter/img3.png" alt="numpy">

<img src="https://7463-tcb-nkd87viq9wheg653bca0d-a8621b-1304207482.tcb.qcloud.la/Serverless-Jupyter/img4.png" alt="scipy">


</appdetail>

<devgroup>

## 开发者社区

您如果有关于错误的反馈或者未来的期待，您可以在 [Serverless Devs repo Issues](https://github.com/serverless-devs/serverless-devs/issues) 中进行反馈和交流。如果您想要加入我们的讨论组或者了解 FC 组件的最新动态，您可以通过以下渠道进行：

<p align="center">

| <img src="https://serverless-article-picture.oss-cn-hangzhou.aliyuncs.com/1635407298906_20211028074819117230.png" width="130px" > | <img src="https://serverless-article-picture.oss-cn-hangzhou.aliyuncs.com/1635407044136_20211028074404326599.png" width="130px" > | <img src="https://serverless-article-picture.oss-cn-hangzhou.aliyuncs.com/1635407252200_20211028074732517533.png" width="130px" > |
|--- | --- | --- |
| <center>微信公众号：`serverless`</center> | <center>微信小助手：`xiaojiangwh`</center> | <center>钉钉交流群：`33947367`</center> | 

</p>

</devgroup>