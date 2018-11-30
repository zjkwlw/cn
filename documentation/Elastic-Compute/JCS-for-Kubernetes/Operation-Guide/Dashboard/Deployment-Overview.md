# Deployment概述
Deployment 为 Pod 和 ReplicaSet 提供了一个声明式定义方法，用来替代以前的ReplicationController来方便的管理应用。  
典型的应用场景包括：  
- 定义Deployment来创建Pod和ReplicaSet  
- 滚动升级和回滚应用  
- 扩容和缩容  
- 暂停和继续Deployment  

