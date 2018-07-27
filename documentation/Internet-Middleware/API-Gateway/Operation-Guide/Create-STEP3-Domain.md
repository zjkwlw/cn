# 自定义域名

API网关基于 API分组，来绑定域名。API网关通过域名来定位到一个唯一的 API分组，再通过Path+HTTPMethod 确定唯一的 API。如果您需要开放 API 则需要为分组绑定独立域名。独立域名需要满足以下几点：
- 独立域名要 CNAME 解析到该分组的二级域名上，然后操作绑定。先解析，后绑定，否则无法绑定。
- 若您需要将其他分组的独立域名变更到当前分组，需要先变更解析，才能成功绑定。


## 绑定过程 
### 操作步骤：
1.找到需要进行绑定域名的分组：
![APIgroup列表页](https://github.com/jdcloudcom/cn/blob/edit/image/Internet-Middleware/API-Gateway/apigroup-rp-apigroup-list.png)

2.点击该分组行的操作 **绑定域名**，选择需要映射的域名并进行绑定。如果没有可用域名，可在自定义域名页面中新增自定义域名，然后再来绑定域名。

![绑定域名](https://github.com/jdcloudcom/cn/blob/edit/image/Internet-Middleware/API-Gateway/apigroup-bdym.png)


## 新增自定义域名过程
### 操作步骤：
1.进入API分组的详情页，点击 自定义域名   **tab签** 。

![域名list](https://github.com/jdcloudcom/cn/blob/edit/image/Internet-Middleware/API-Gateway/zdyym-list.png)

2.点击   **添加域名** 进行新增。目前每个分组支持最多绑定5个自定义域名

![域名list](https://github.com/jdcloudcom/cn/blob/edit/image/Internet-Middleware/API-Gateway/zdyym-add.png)


