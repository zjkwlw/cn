# 验证配置生效

此步骤**不是必须步骤**，但是为了最大程度保证业务的稳定，我们建议在修改DNS解析前先进行本地的测试。

## 前提条件
- 已成功购买了IP高防，计费状态正常，且已配置好转发规则。

## 操作步骤
1. 登录 [IP高防 控制台](https://ip-anti-console.jdcloud.com/instancelist)。
2. 在“实例列表”页面，选择目标实例，点击 **实例名称** 或**转发配置**，进入实例详情页面。
![网站类实例](https://github.com/jdcloudcom/cn/blob/edit/image/Advanced%20Anti-DDoS/web-rule%2001.png)。
3. 请在下图红框处所示，获取需要加入白名单的IP高防回源IP段。


## 相关参考
- [入门概述](Overview.md)
- [创建实例](Create-Instance.md)
- [非网站类规则](Non-Web-Service-Forwarding-Rule.md)
- [网站类规则](Web-Service-Forwarding-Rule.md)
- [放行回源IP](Whitelist-local-IP-subnet.md)
- [计费规则](../../Pricing/Billing-Rules.md)
