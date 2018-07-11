# 无法连接云数据库 MongoDB

## 现象描述
使用云主机连接数据库报错，出现：exception: connect failed，具体参考下图。
![](https://github.com/jdcloudcom/cn/blob/master/image/mongodb/mongo-027.png)

## 原因分析
云主机到数据库的链路不通。

## 处理步骤

1. 确认用于连接的云主机是否与 MongoDB 实例是否在同一个VPC。

   在京东云控制台查看云主机与 MongoDB 实例是否处于同一个VPC内，如两者处于不同VPC，且未通过VPC对等连接打通，则内则网络不通，请更换用于连接的云主机。

1. 确认 MongoDB 实例的白名单是否限制了云主机的IP？

   在 MongoDB 控制台找到该 MongoDB实例，查看其白名单设置。确认云主机的内网IP是否被白名单限制，如受限，请将其加入白名单。

1. 确认云主机的安全组规则是否做了限制。

   在云主机控制台，找到台该云主机，查看其安全组规则，如出站规则未开通27017端口，请添加规则：
   - 类型：自定义TCP
   - 目的端口：27017
   - 目的IP：0.0.0.0/0，因MongoDB 实例在自动容灾切换或扩容时IP可能会变化，请开通全部IP。
	![](https://github.com/jdcloudcom/cn/blob/master/image/mongodb/mongo-028.png)
	
1. 确认云主机与MongoDB所在子网使用的网络 ACL 是否做了限制。

   在私有网络控制台，找到云主机和 MongoDB 所在的子网使用的网络ACL，确认其出站规则与入站规则是否开通27017端口，如未开通，请添加规则：
   - 类型：自定义TCP
   - 目的端口：27017
   - 目的IP：0.0.0.0/0，因MongoDB 实例在自动容灾切换或扩容时IP可能会变化，请开通全部IP。
   ![](https://github.com/jdcloudcom/cn/blob/master/image/mongodb/mongo-029.png)

