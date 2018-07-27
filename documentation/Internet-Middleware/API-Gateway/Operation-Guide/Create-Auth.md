# API的访问授权

API提供方给API调用方授权应用

访问密钥（APIKey/APISecret）代表请求者的身份。

当您的客户或者您自己测试调用 API 时，都需要创建 访问密钥 作为请求者的身份，然后由您在访问授权中，授权API分组给 API调用者使用。


## 操作步骤
1.获取API调用者的访问密钥ID 或者 京东云账户的Access Key。

【访问密钥ID】

![访问密钥详情页](https://github.com/jdcloudcom/cn/blob/edit/image/Internet-Middleware/API-Gateway/fwmy-xqy.png)
 
【Access Key】

![AK List](https://github.com/jdcloudcom/cn/blob/edit/image/Internet-Middleware/API-Gateway/AK-list.png)
 


 
2.在授权操作页面，选择一个或者多个准备开放调用权限的 API，选定 测试/线上。
API提供者在 **访问授权**页，给API调用者进行授权绑定

![访问授权页](https://github.com/jdcloudcom/cn/blob/edit/image/Internet-Middleware/API-Gateway/fwsq-list.png)

3.点击 **创建授权**，在授权中，填入API调用者的访问密钥。

![创建授权](https://github.com/jdcloudcom/cn/blob/edit/image/Internet-Middleware/API-Gateway/fwsq-add.png)


4.密钥创建成功后，点击 **绑定**进行授权分组的绑定关系。

![授权绑定](https://github.com/jdcloudcom/cn/blob/edit/image/Internet-Middleware/API-Gateway/fwsq-bd.png)


  
