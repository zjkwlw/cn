# 创建Topic
  在Topic管理页面可以进行topic的创建

## 操作步骤
### 1.Topic管理页面点击“新建”按钮
从控制台左侧菜单中，找到互联网中间件-消息队列 JCQ-Topic管理页面，点击新建
 ![创建topic步骤1](https://github.com/jdcloudcom/cn/blob/edit/image/Internet-Middleware/Message-Queue/创建topic-01.PNG)

### 2.填写完Topic信息，点击“创建”按钮
页面刷新，完成新topic的创建
 ![创建topic步骤2](https://github.com/jdcloudcom/cn/blob/edit/image/Internet-Middleware/Message-Queue/创建topic-02.png)  
topic名称可以按照提示信息输入，不可修改。  
消息类型分为无序消息和全局顺序消息：  
- 无序消息：不保证先入先出（FIFO）的顺序消费，包含普通消息和延时消息。
- 全局顺序消息：消息的生产和消费按照消息的发布顺序进行（FIFO）。
备注根据需求填写，不可超过255个字节。
