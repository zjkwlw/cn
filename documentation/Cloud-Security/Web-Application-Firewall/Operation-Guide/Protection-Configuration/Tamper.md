## **网站防篡改**

您可以使用网站防篡改对指定的敏感页面设置缓存，缓存后即使源站页面内容被恶意篡改，WAF也会向访问者返回预先缓存好的页面内容，确保用户看到正确的页面。

### **操作步骤**

参照以下步骤，启用并配置网站防篡改：

**说明：** 执行以下操作前，请确保已将网站接入WAF进行防护。具体操作请参考[CNAME接入指南](file:///E:\WMM\%E5%B7%A5%E4%BD%9C%E6%80%BB%E7%BB%93\WAF%E6%96%87%E6%A1%A3\%E4%BA%91WAF\Introduction\%E9%98%B2%E6%8A%A4%E9%85%8D%E7%BD%AE\intl.zh-CN\%E7%94%A8%E6%88%B7%E6%8C%87%E5%8D%97\%E6%8E%A5%E5%85%A5WAF\CNAME%E6%8E%A5%E5%85%A5%E6%8C%87%E5%8D%97.md)。

1. 登录[京东云Web应用防火墙控制台](https://cloudwaf-console.jdcloud.com)。

2. 前往**网站配置**页面。

3. 选择要操作的域名，单击其操作列下的**防护配置**。

4. 在**网站防篡改**下，启用防护，并单击**前去配置**。 **说明：** 如果您不想使用网站防篡改，您可以在该页面关闭防护。![img](file:///C:\Users\ZHANGJ~1\AppData\Local\Temp\msohtmlclip1\01\clip_image002.jpg)

5. 单击**新增规则**，在添加URL对话框配置要防护的具体页面。![img](file:///C:\Users\ZHANGJ~1\AppData\Local\Temp\msohtmlclip1\01\clip_image004.png)

6. - **规则名称**：为该规则命名。
   - **URL**：填写精确的要防护的路径。

7. 添加规则后，手动打开对应规则**防护状态**下的开关。如果您在添加规则后未打开防护开关，则设置不会生效。![img](file:///C:\Users\ZHANGJ~1\AppData\Local\Temp\msohtmlclip1\01\clip_image006.png)

8. 如果被防护页面进行了内容更新，您必须单击**更新缓存**来更新缓存。如果您在页面更新后未更新缓存，WAF将始终返回最近一次缓存的页面内容。![img](file:///C:\Users\ZHANGJ~1\AppData\Local\Temp\msohtmlclip1\01\clip_image008.png)

**相关参考**

- [产品简介](https://github.com/jdcloudcom/cn/blob/edit/documentation/Cloud-Security/Advanced-Anti-DDoS/Introduction/What-Is-Advanced-Anti-DDoS.md)
- [产品定价](https://github.com/jdcloudcom/cn/blob/edit/documentation/Cloud-Security/Advanced-Anti-DDoS/Pricing/Billing-Rules.md)
- [常见问题](https://github.com/jdcloudcom/cn/blob/edit/documentation/Cloud-Security/Advanced-Anti-DDoS/Pricing/Billing-Rules.md)

 