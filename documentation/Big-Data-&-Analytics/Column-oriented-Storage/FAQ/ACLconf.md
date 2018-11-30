# 常见问题

### 如何配置ACL？

1.	创建VPC
请参考帮助中心文档：[VPC配置](/documentation/Networking/Virtual-Private-Cloud/Operation-Guide/VPC-Configuration.md)

2.	创建子网
请参考帮助中心文档：[子网配置](/documentation/Networking/Virtual-Private-Cloud/Operation-Guide/Subnet-Configuration.md)

3.	创建ACL
请参考帮助中心文档：[网络ACL配置](/documentation/Networking/Virtual-Private-Cloud/Operation-Guide/Network-ACL-Configuration.md)

4.	配置ACL规则
入站规则：
1)	必须配置的规则：

优先级|类型|	协议|	目标端口|	源IP|	策略
:---|:---|:---|:---|:---|:---
1	|ssh	|TCP	|22	|0.0.0.0/0|	接受
2	|ALL ICMP|ALL ICMP	|-	|0.0.0.0/0|	接受
3	|ALL traffic|	ALL traffic	|1-65535	|103.224.222.0/24|	接受
4	|ALL traffic	|ALL traffic	|1-65535	|100.65.0.0/16	|接受
5	|ALL traffic	|ALL traffic	|1-65535	|100.64.0.0/16	|接受

2)	根据用户需要配置的规则：

优先级|类型|	协议|	目标端口|	源IP|	策略
:---|:---|:---|:---|:---|:---
6	|ALL traffic|	ALL traffic	|1-65535	|用户网络出口IP（CIDR格式）|	接受
