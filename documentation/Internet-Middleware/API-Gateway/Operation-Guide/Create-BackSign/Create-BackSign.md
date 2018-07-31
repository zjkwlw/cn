# 后端服务签名


目前 API 网关为您配置安全防护设置，提供了两种安全措施：后端签名密钥和流控策略。本章将介绍后端签名。

后端签名密钥采用京东云用户AK/SK(Access Key/Access Key Secret) 在网关请求您的真实后端时，通过后端签名校验保障您后端的安全。

您将京东云用户AK/SK密钥绑定到 API 上后，当网关请求这个 API 时，会添加并出示该AK/SK，您的后端通过验证签名字符串来验证网关的身份。


## 操作步骤

点击左侧 **后端签名**，进行后端签名的配置和绑定

1.进入后端签名列表页

![后端签名列表页](https://github.com/jdcloudcom/cn/blob/edit/image/Internet-Middleware/API-Gateway/hdqm-list.png)


2.新增后端签名

![新增后端签名](https://github.com/jdcloudcom/cn/blob/edit/image/Internet-Middleware/API-Gateway/hdqm-add.png)


3.给分组绑定签名

![绑定签名](https://github.com/jdcloudcom/cn/blob/edit/image/Internet-Middleware/API-Gateway/hdqm-bd.png)



  
