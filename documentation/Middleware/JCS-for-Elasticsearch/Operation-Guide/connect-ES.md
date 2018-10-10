## 访问集群
### 基于云服务器访问前提
京东云搜索Elasticsearch与依赖的云主机必须处于同一个VPC下，因此要先创建相同私有网络和子网的云主机，从该云主机下获取到“公网IP”，才能访问云搜索Elasticsearch服务。
### curl连接测试
通过Linux环境下的curl命令访问云搜索Elasticsearch实例的9200端口。
指定账号密码访问示例格式为curl –XGET [公网域名]，公网域名为云搜索Elasticsearch中基本信息界面的**内网访问域名**，指令示例如下：
```
curl -XGET es-nlb-es-kgqo8zmgcv.jvessel-open-hb.jdcloud.com:9200
```
响应如下代表访问成功：
```
{
  =^.^=
/_cat/allocation
/_cat/shards
/_cat/shards/{index}
/_cat/master
/_cat/nodes
/_cat/tasks
/_cat/indices
/_cat/indices/{index}
/_cat/segments
/_cat/segments/{index}
/_cat/count
/_cat/count/{index}
/_cat/recovery
/_cat/recovery/{index}

```
### 数据加载到ES
访问成功后，将数据集（accounts.json）通过curl命令导入到该虚拟机下，将它解压缩到我们当前的目录，然后将加载到我们的集群中，如下所示：
```
curl -H“Content-Type：application / json”-XPOST“es-nlb-es-kgqo8zmgcv.jvessel-open-hb.jdcloud.com：9200 / bank / account / _bulk？pretty＆refresh”--data-binary“@ accounts.json”
curl “es-nlb-es-kgqo8zmgcv.jvessel-open-hb.jdcloud.com：9200 / _cat / indices？v”
```
这意味着我们只是成功地将1000个文档批量索引到银行索引（在帐户类型下），即数据成功加载到ES集群。

