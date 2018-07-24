# 应用场景

以下说明网络负载均衡NLB的适用场景。

## 千万级并发流量、自动弹性伸缩业务
京东云网络负载均衡NLB专用于提供四层千万级高并发业务服务，能够感知用户业务量的变化、自动按需弹性伸缩，以便平滑、动态地支持用户业务访问量的变化。京东云NLB在支持自动弹缩的同时，还提供了强有力的会话保持能力，能够有效减小用户业务开发中对于会话保持的考虑与研发工作量，提升研发效率、加快业务面市节奏。网络负载均衡适合游戏、电商等高并发服务需求，同时也适用于秒杀等流量快速增减的动态服务场景。
![同城容灾场景](https://github.com/jdcloudcom/cn/blob/master/image/mongodb/mogno-001.png)


## 高可用业务部署

京东云网络负载均衡NLB服务支持自主选择冗余配置、多可用区部署，支持高可用；绑定高可用组AG即可支持后端服务同机房跨机架、跨可用区的多维度高可用部署，消除后端服务实例由于单点设备故障造成的影响。高可用组还支持服务实例按照指定模板自动进行高可用分布的弹性伸缩能力，与负载均衡完美搭档，提供高可用、可自动伸缩的服务。NLB+AG的高可用业务部署架构，适用于所有需要提供稳定、高容错能力的业务场景，如政务服务、企业应用、互联网应用等。

![分服应用场景](https://github.com/jdcloudcom/cn/blob/master/image/mongodb/mongo-002.png)

## 相关参考

- [产品优势](../Product-Introduction/Benefits.md)
- [产品功能](../Product-Introduction/Functions.md)
- [价格总览](../Pricing/Price-Overview.md)
- [计费规则](../Pricing/Billing-Rules.md)
- [创建实例](../Getting-Started/Create-Instance.md)
