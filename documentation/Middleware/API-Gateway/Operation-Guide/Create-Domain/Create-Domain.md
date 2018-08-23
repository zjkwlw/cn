# 自定义域名

API网关提供基于 API分组的域名绑定。API网关通过域名来定位到一个唯一的 API分组，再通过Path+HTTPMethod 确定唯一的 API。独立域名需要满足以下几点：
- 独立域名要 CNAME 解析到该分组的二级域名上，然后操作绑定。先解析，后绑定，否则无法绑定。
- 一个域名只能绑定在一个分组上。
- 每个分组最多支持5各自定义域名绑定。如需增加可通过工单申请。
- 域名必须备案，才能绑定成功。
- 自定义域名仅支持线上环境，其它环境（测试、预发）暂不支持。


## 应用场景
通过自定义域名用户可以解决以下问题：

1.用户A拥有一个域名为abc.com的网站，此时需要将对网站中图片的请求迁移到OSS，并且不想修改任何网页的代码，即对外链接不变。此时可使用CNAME功能。

2.避免业务中可能涉及的跨域或者安全问题。

3.用户不希望展示oss域名，希望使用自己的域名。



## 前提条件 
开通京东云对象存储并且未欠费用户


## 新增自定义域名过程
### 操作步骤：
#### STEP1:进入API分组的详情页，点击 自定义域名   **tab签** 。

![域名list](https://github.com/jdcloudcom/cn/blob/edit/image/Internet-Middleware/API-Gateway/zdyym-list.png)

#### STEP2:点击   **添加域名** 进行新增。目前每个分组支持最多绑定5个自定义域名

![域名list](https://github.com/jdcloudcom/cn/blob/edit/image/Internet-Middleware/API-Gateway/zdyym-add.png)



## 绑定过程 
### 操作步骤：
#### STEP1:找到需要进行绑定域名的分组：
![APIgroup列表页](https://github.com/jdcloudcom/cn/blob/edit/image/Internet-Middleware/API-Gateway/apigroup-rp-apigroup-list.png)

#### STEP2:绑定域名
点击该分组行的操作 **绑定域名**，选择需要映射的域名并进行绑定。如果没有可用域名，可在自定义域名页面中新增自定义域名，然后再来绑定域名。

![绑定域名](https://github.com/jdcloudcom/cn/blob/edit/image/Internet-Middleware/API-Gateway/apigroup-bdym.png)

