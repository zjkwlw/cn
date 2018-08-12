# 资源监控
资源监控是对用户名下云资源的各项指标进行监控。用户可在资源监控列表中选择某类资源，对该类资源下某一资源的监控图表和报警详情进行查看。用户可根据各类资源的特性针对不同监控项设置报警规则和联系人，当设置的监控项指标的数据触发了报警，则向指定的报警联系人发送短信和邮件通知。
## 查看资源监控图表
资源的监控图表可通过两种方式进行查看，一种是在云监控页面进行查看，一种是在资源内查看。
### 云监控页面查看
1. 登录京东云控制台，点击管理->云监控->资源监控菜单，选择待查看的资源类型，进入资源的监控列表。

![image](https://raw.githubusercontent.com/jdcloudcom/cn/edit/image/Cloud-Monitor/yunziyuan/1.%E8%B5%84%E6%BA%90%E7%9B%91%E6%8E%A7.png)

2. 点击各实例的操作列的“监控表”，即可看到该实例各指标的监控数据。

![image](https://raw.githubusercontent.com/jdcloudcom/cn/edit/image/Cloud-Monitor/yunziyuan/2.%E8%B5%84%E6%BA%90%E7%9B%91%E6%8E%A7.png)

### 资源内查看
1. 登录京东云控制台，进入云监控模块下的资源监控，选择某类资源进入该类资源的资源列表，查看某一资源的详情。

![image](https://raw.githubusercontent.com/jdcloudcom/cn/edit/image/Cloud-Monitor/yunziyuan/3.%E8%B5%84%E6%BA%90%E7%9B%91%E6%8E%A7.png)

2. 在云资源详情页面，切换至“监控”标签页，即可看到该实例各项监控指标的实时数据。


## 对资源设置监控报警
### 增加报警规则
1. 登录京东云控制台，点击管理->云监控->资源监控菜单，选择待查看的资源类型，进入资源的监控列表。点击操作列的“报警规则”。
 
![image](https://raw.githubusercontent.com/jdcloudcom/cn/edit/image/Cloud-Monitor/yunziyuan/4.%E8%B5%84%E6%BA%90%E7%9B%91%E6%8E%A7.png)
   
2. 进入监控详情的报警规则页面，点击“新增报警规则”，可以创建报警规则。

![image](https://raw.githubusercontent.com/jdcloudcom/cn/zhangwenjie30-patch-4/image/Cloud-Monitor/yunziyuan/%E5%AE%9E%E4%BE%8B%E8%AF%A6%E6%83%85_%E6%8A%A5%E8%AD%A6%E8%A7%84%E5%88%99.png)

3. 输入监控项、统计周期、统计方法、计算方式、阈值、持续周期，根据业务需求也可设置分级报警（分为一般、严重、紧急），点击“下一步”添加报警规则及联系人，点击“下一步”，点击“完成”即可。 

![image]()

4. 添加成功后，可在报警规则列表中，可查看到设置的规则信息。 

### 修改/删除/禁用报警规则
1. 登录京东云控制台，点击管理->云监控->资源监控菜单，选择待查看的资源类型，在资源列表中点击“报警规则”，进入监控详情的报警规则页面，进入资源的监控列表。

![image](https://raw.githubusercontent.com/jdcloudcom/cn/zhangwenjie30-patch-4/image/Cloud-Monitor/yunziyuan/%E5%AE%9E%E4%BE%8B%E8%AF%A6%E6%83%85_%E6%8A%A5%E8%AD%A6%E8%A7%84%E5%88%99.png)

2. 点击操作列更多操作下的“修改”按钮，可根据需要修改监控项、统计周期、统计方法、计算方式、阈值、持续周期、报警联系人信息。
3. 点击操作列更多操作下的“删除”按钮，即可删除。
3. 点击操作列更多操作下的“禁用”按钮，即可禁用规则。

![image](https://raw.githubusercontent.com/jdcloudcom/cn/edit/image/Cloud-Monitor/yunziyuan/6.%E8%B5%84%E6%BA%90%E7%9B%91%E6%8E%A7.png)

### 管理报警联系人/组
登录京东云账号后，在页面右上侧查看账户信息下拉框，点击账号管理-联系人管理，可在此页面查看并管理联系人及联系组。

![image](https://raw.githubusercontent.com/jdcloudcom/cn/edit/image/Cloud-Monitor/yunziyuan/7.%E8%B5%84%E6%BA%90%E7%9B%91%E6%8E%A7.png)

### 添加/使用报警模板
1. 在设置报警规则页面，根据需要设置监控项、统计周期、统计方法、计算方式、阈值、持续周期，完成后勾选“保存为新的报警规则模板”将该规则保存为模板。

![image](https://raw.githubusercontent.com/jdcloudcom/cn/edit/image/Cloud-Monitor/yunziyuan/8.%E8%B5%84%E6%BA%90%E7%9B%91%E6%8E%A7.png)

2. 已有报警模板后，可在新增报警规则页面，勾选“使用已有的报警规则模板”选择已有模板进行使用。
 
![image](https://raw.githubusercontent.com/jdcloudcom/cn/edit/image/Cloud-Monitor/yunziyuan/9.%E8%B5%84%E6%BA%90%E7%9B%91%E6%8E%A7.png)
