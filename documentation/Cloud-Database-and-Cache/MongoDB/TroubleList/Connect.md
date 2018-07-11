# 无法连接云数据库 MongoDB？

## 问题描述
使用云主机连接数据库报错？
![](https://github.com/jdcloudcom/cn/blob/master/image/mongodb/mongo-027.png)


## 问题排查

1. 确认用于连接的云主机是否与云数据库在同一个VPC内？如处于不同VPC内则网络不通。
1. 确认 MongoDB 实例的白名单是否限制了云主机的IP？如云主机IP受限，请添加IP至白名单。
1. 确认云主机的安全组规则是否做了限制？如出站规则未开通27017端口，请添加
   - 类型：自定义TCP
   - 目的端口：27017
   - 目的IP：0.0.0.0/0，因MongoDB 实例在自动容灾切换或扩容时IP可能会变化，请开通全部IP。
	![](https://github.com/jdcloudcom/cn/blob/master/image/mongodb/mongo-028.png)
	
1. 云主机与MongoDB所在子网的ACL规则是否做了限制？在出站规则与入站规则中，开通27017端口，请添加：
   - 类型：自定义TCP
   - 目的端口：27017
   - 目的IP：0.0.0.0/0，因MongoDB 实例在自动容灾切换或扩容时IP可能会变化，请开通全部IP。
   ![](https://github.com/jdcloudcom/cn/blob/master/image/mongodb/mongo-029.png)

