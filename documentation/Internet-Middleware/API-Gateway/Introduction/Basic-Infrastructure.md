# 基础架构
API网关提供API定义者服务和API调用者服务。API定义者通过管理和部署API分组，提供API的调用;API调用者，通过访问密钥和API定义者的授权访问，使用API。

## 业务架构
业务架构如下图：
![](https://github.com/jdcloudcom/cn/blob/master/image/mongodb/mongo-000.jpg)
![](https://github.com/jdcloudcom/cn/blob/edit/image/Internet-Middleware/API-Gateway/%E4%BA%A7%E5%93%81%E6%9E%B6%E6%9E%84.png)

|名称|描述|
| - | - | 
|控制服务| 支持 MongoDB 实例的多种管理控制任务，包括创建、删除、查询、配置变更、容灾切换、备份与恢复等任务。|
|监控服务|收集 MongoDB 实例信息（资源使用和数据库键统计信息等）和物理机信息（资源使用信息和评分等），前者供用户和控制台展现，后者用于系统管理。|
|Sentinel| Sentinel 监控 MongoDB 实例是否存活，多个哨兵同时工作，当发现节点不可用时，发送 failover 任务，自动创建新节点，并同步数据。|
|备份服务| 自动定时备份，以及支持用户手动创建备份。|
|日志收集| 收集 MongoDB 实例的运行情况的日志信息。|
|数据迁移| 当主从节点都不可用的时候，或者需要克隆在线运行的实例时，在线迁移系统负责实例重新搭建及数据迁移任务，保证业务不受影响。|

## 相关参考

- [产品优势](../Introduction/Benefits.md)
- [产品功能](../Introduction/Functions.md)
- [价格总览](../Pricing/Price-Overview.md)
- [计费规则](../Pricing/Billing-Rules.md)
- [创建实例](../Getting-Started/Create-Instance.md)



