# 创建账号


MongoDB 实例的账号不通过 MongoDB 控制台管理。
在创建实例时，系统已为您创建了 root 账号，拥有 MongoDB 的 root 权限，您可以使用此账号登录数据库后，创建其他账号。

## 创建账号命令

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

## 示例

### 创建管理员账号

```
use admin
db.createUser(
     {
       user: "<name>"，
       pwd:"<cleartext password>",
       roles:[{role:"root",db:"admin"}]
     }
)
```  


### 创建数据库用户

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

## 常用角色

- 数据库用户角色：read，readWrite
- 数据库管理员角色：dbAdmin，dbOwner，userAdmin
- 集群管理员角色：clusterAdmin，clusterManager，clusterMonitor，hostManager
- 备份恢复角色：backup，restore
- 所有库角色：readAnyDatabase，readWriteAnyDatabase,userAdminAnyDatabase,dbAdminAnyDatabase
- 超级管理员角色：root 


关于MongoDB创建用户的详情说明请参见“ [MongoDB官方文档](https://docs.mongodb.com/v3.2/reference/method/db.createUser/#local-database)”。







	

	




	
	


