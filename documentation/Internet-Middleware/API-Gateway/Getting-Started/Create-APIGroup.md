# 开放API

您可以通过创建和部署API分组，实现服务的对外开放。
本文将快速引导您通过控制台开放API。
您需要依次完成以下步骤才能成功开放API服务：
- STEP1:创建API分组
- STEP2:创建分组下的API
- STEP3：给分组绑定域名、配置流控策略、后端签名
- STEP4：发布API分组到环境上
- STEP5：给API调用者授权访问


## 前提条件
- 已注册京东云账号，并完成实名认证。如果还没有账号请 [注册](https://accounts.jdcloud.com/p/regPage?source=jdcloud&ReturnUrl=%2f%2fuc.jdcloud.com%2fpassport%2fcomplete%3freturnUrl%3dhttp%3A%2F%2Fuc.jdcloud.com%2Fredirect%2FloginRouter%3FreturnUrl%3Dhttps%253A%252F%252Fwww.jdcloud.com%252Fhelp%252Fdetail%252F734%252FisCatalog%252F1)，或 [实名认证](https://uc.jdcloud.com/account/certify)。


## 操作步骤
### STEP1:创建API分组
1. 登录 [API网关 控制台](https://apigateway-console.jdcloud.com/apiGroupList)。
 ![API分组管理](https://github.com/jdcloudcom/cn/blob/edit/image/Internet-Middleware/API-Gateway/apigroup-1.png)
 
 
2. 在“API分组管理”页面，点击 **新建API分组** ，进入“创建”页面。
![创建分组](https://github.com/jdcloudcom/cn/blob/edit/image/Internet-Middleware/API-Gateway/apigroup-addgroup.png)
    
    
3.填写分组信息后，点击保存，即新建分组。当首次新建时，系统会自动将其保存为版本号为0.0.1的版本。后续可在版本管理中进行多版本维护。



### STEP2:创建分组下的API
1.找到分组，点击该分组行的操作 **管理API**，进入“API列表”页
 ![API列表](https://github.com/jdcloudcom/cn/blob/edit/image/Internet-Middleware/API-Gateway/apigroup-apilist.png)


2. 在“API列表”页面，点击 **新建API** ，进入创建API页面。
![创建分组](https://github.com/jdcloudcom/cn/blob/edit/image/Internet-Middleware/API-Gateway/apigroup-addapi.png)


3.填写API信息后，点击保存，即新建完成。



### STEP2:创建分组下的API
1.找到分组，点击该分组行的操作 **管理API**，进入“API列表”页
 ![API列表](https://github.com/jdcloudcom/cn/blob/edit/image/Internet-Middleware/API-Gateway/apigroup-apilist.png)


2. 在“API列表”页面，点击 **新建API** ，进入创建API页面。
![新建API](https://github.com/jdcloudcom/cn/blob/edit/image/Internet-Middleware/API-Gateway/apigroup-addapi.png)


3. 新建成功后，再点击新增的API进入API详情页，并进行高级选项配置。该项目可选是否配置，但当需要进行实际发布时该信息项需要配置。
![高级配置](https://github.com/jdcloudcom/cn/blob/edit/image/Internet-Middleware/API-Gateway/apigroup-addapi-advane.png)
  
  
4.填写API信息后，点击保存，即新建完成。




### STEP3:给分组绑定域名、配置流控策略、后端签名
1.找到分组，点击该分组行的操作 **绑定域名**，进行绑定
![APIgroup列表页](https://github.com/jdcloudcom/cn/blob/edit/image/Internet-Middleware/API-Gateway/apigroup-rp-apigroup-list.png)
选择需要映射的域名并进行绑定。如果没有可用域名，可在自定义域名页面中新增自定义域名，然后再来绑定域名。
![绑定域名](https://github.com/jdcloudcom/cn/blob/edit/image/Internet-Middleware/API-Gateway/apigroup-bdym.png)


2.点击左侧 **流控策略**，进行流控策略配置和绑定
（1）流控策略列表页
![流控策略列表页](https://github.com/jdcloudcom/cn/blob/edit/image/Internet-Middleware/API-Gateway/lkcl-list.png)


（2）新增流控策略
![新增策略](https://github.com/jdcloudcom/cn/blob/edit/image/Internet-Middleware/API-Gateway/lkcl-add.png)


（3）给分组绑定策略
![绑定策略](https://github.com/jdcloudcom/cn/blob/edit/image/Internet-Middleware/API-Gateway/lkcl-bd.png)


3.点击左侧 **后端签名**，进行后端签名的配置和绑定
（1）后端签名列表页
![后端签名列表页](https://github.com/jdcloudcom/cn/blob/edit/image/Internet-Middleware/API-Gateway/hdqm-list.png)


（2）新增后端签名
![新增后端签名](https://github.com/jdcloudcom/cn/blob/edit/image/Internet-Middleware/API-Gateway/hdqm-add.png)


（3）给分组绑定签名
![绑定策略](https://github.com/jdcloudcom/cn/blob/edit/image/Internet-Middleware/API-Gateway/hdqm-bd.png)



