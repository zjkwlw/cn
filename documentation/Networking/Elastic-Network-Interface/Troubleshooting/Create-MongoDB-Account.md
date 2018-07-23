# 如何创建 MongoDB 数据库账号

## 问题描述

MongoDB 控制台未提供账号管理功能，我如何创建 MongoDB 数据库账号？

## 问题处理

云数据库 MongoDB 默认为您提供了root账号，拥有MongoDB的root权限，您可以使用root账号登录数据库后，创建其他账号。

### 创建账号命令

> db.createUser(user, writeConcern)

user文档格式如下
```
 { user: "<name>",
   pwd: "<cleartext password>",
   customData: { <any information> },
   roles: [
     { role: "<role>", db: "<database>" } | "<role>",
     ...
   ]
 }
```

### 示例

#### 创建管理员账号

```
use admin
db.createUser(
     {
       user: "<name>"
         pwd:"<cleartext password>",
       roles:[{role:"root",db:"admin"}]
     }
  )
```  


#### 创建数据库用户

指定数据库创建用户，该用户只能访问该数据库。
```
 use test
 db.createUser(
    {
      user: "<name>",
      pwd: "<cleartext password>",
      roles: ["readWrite", "dbAdmin"]
    }
 ) 
```

### 常用角色

- 数据库用户角色：read，readWrite
- 数据库管理员角色：dbAdmin，dbOwner，userAdmin
- 集群管理员角色：clusterAdmin，clusterManager，clusterMonitor，hostManager
- 备份恢复角色：backup，restore
- 所有库角色：readAnyDatabase，readWriteAnyDatabase,userAdminAnyDatabase,dbAdminAnyDatabase
- 超级管理员角色：root 


关于MongoDb创建用户的详情说明请参考 [MongoDB官方文档](https://docs.mongodb.com/v3.2/reference/method/db.createUser/#local-database)










	

	




	
	


