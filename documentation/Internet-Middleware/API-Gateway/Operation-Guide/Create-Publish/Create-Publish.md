# 发布API分组

API分组信息创建完成后，您可以通过在测试、预发、线上环境中，测试和正式上线 API。


## 操作步骤：

1.调试

您可以把 API 发布到测试环境进行调试，然后调试 API。

首先，在 **API分组管理**页，点击操作中的 **发布**：

![APIgroup列表页](https://github.com/jdcloudcom/cn/blob/edit/image/Internet-Middleware/API-Gateway/apigroup-rp-apigroup-list.png)

然后，选择需要发布的环境（如，测试），选择要发布的版本，配置后端地址，然后点击发布，即可将分组发布到环境中。

![发布](https://github.com/jdcloudcom/cn/blob/edit/image/Internet-Middleware/API-Gateway/apigroup-fb.png)

注意：调试时，可以在选择 Mock后端方式进行发布，则调试时不会去请求真实后端服务，而会直接返回常量结果。这种方式适用于调试 API 的请求链路是否正确，会跳过 APP 鉴权 和 签名校验 环节。




2.测试

为了模拟真实的用户请求，您可以自己以API调用者身份创建一个 授权密钥，并绑定授权密钥和API分组。

然后按照真实的请求场景，写代码或者基于网关提供的 SDK 样例 请求 API。

您可以将 API 发布到测试或者线上环境，在绑定独立域名之前，可以直接访问二级域名来进行测试调用。请求时注意指定环境，若不指定则默认为访问线上。



3.发布

完成测试后，您就可以正式发布API分组到线上环境 。发布完成后，可在部署管理页中，看到各个环境的部署情况。
![部署列表](https://github.com/jdcloudcom/cn/blob/edit/image/Internet-Middleware/API-Gateway/bslb-list.png)

API 网关支持对测试/线上的 API 做版本管理，您可以发布 API、下线 API 还可以切换版本，切换版本是实时生效。
![切换版本](https://github.com/jdcloudcom/cn/blob/edit/image/Internet-Middleware/API-Gateway/bslb-qhbb.png)

如需下线，可直接点击下线操作。
![下线](https://github.com/jdcloudcom/cn/blob/edit/image/Internet-Middleware/API-Gateway/bslb-xx.png)


