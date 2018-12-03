# Deployment概述
Deployment 为 Pod 和 ReplicaSet 提供了一个声明式定义方法，用来替代以前的ReplicationController来方便的管理应用。  
典型的应用场景包括：  
- 定义Deployment来创建Pod和ReplicaSet  
- 滚动升级和回滚应用  
- 扩容和缩容  
- 暂停和继续Deployment    
# 创建Deployment  
1. 打出控制台，进入[弹性计算>>Kubernetes集群>>Workloads>>Deployment](https://cns-console.jdcloud.com/host/kubernetesdeployment/list)  
2. 选择Kubernetes集群，（Kubernetes集群创建完后，还请等几分钟后，打开。否则会出现‘内部错误’的报错）  
![]()
3. 
