# 监控

您可以通过登录 JMR 控制台，点击“集群管理”菜单。
本文介绍如何查看集群监控。

## 操作步骤
1. 登录 [JMR 控制台](https://mongodb-console.jdcloud.com/mongodb)，选择查看哪个地域下的集群。

2. 选择您想要查看的集群，对应操作中的“监控”。

	1. 集群监控指标
	
	   说明：
	   - 开启高可用，集群会有两个Master：分别为Active Namenode和Standby Namenode：两台Namenode形成互备，一台处于Active状态，为主Namenode，另一台处于Standby状态，为备Namenode，只有主Namenode才能对外提供读写服务；
	   - 不开启高可用，集群默认有一个Master；
	   - JMR_BD-OS-1.0版本在创建集群的时候，默认选择高可用；
	 ![软件设置](https://github.com/jdcloudcom/cn/blob/master/image/mongodb/mongo-003.png)
	2. 集群节点详情
	 说明：
	   - 高可用；
	   - JMR-BDOS版本可提供一套完整的大数据平台；
	 ![硬件设置](https://github.com/jdcloudcom/cn/blob/master/image/mongodb/mongo-003.png)
	   
	3. 集群服务进程
	
	  ![网络设置](https://github.com/jdcloudcom/cn/blob/master/image/mongodb/mongo-003.png)
	   

## 相关参考

- [设置白名单](https://github.com/jdcloudcom/cn/blob/master/documentation/Cloud-Database-and-Cache/MongoDB/Getting-Started/Whitelist.md)
- [连接实例](https://github.com/jdcloudcom/cn/blob/master/documentation/Cloud-Database-and-Cache/MongoDB/Getting-Started/DatabaseConnection.md)
- [修改密码](https://github.com/jdcloudcom/cn/blob/master/documentation/Cloud-Database-and-Cache/MongoDB/Operation-Guide/Account/ResetPassword.md)
- [导入数据](https://github.com/jdcloudcom/cn/blob/master/documentation/Cloud-Database-and-Cache/MongoDB/Getting-Started/Import-Data.md)
- [变更实例配置](https://github.com/jdcloudcom/cn/blob/master/documentation/Cloud-Database-and-Cache/MongoDB/Operation-Guide/Instance-Management/ModifyInstanceSpec.md)
- [计费规则](https://github.com/jdcloudcom/cn/blob/master/documentation/Cloud-Database-and-Cache/MongoDB/Pricing/Billing-Rules.md)
