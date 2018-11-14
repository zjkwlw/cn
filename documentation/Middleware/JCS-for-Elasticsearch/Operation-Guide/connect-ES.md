## 访问集群
### 基于云服务器访问前提
京东云搜索Elasticsearch与依赖的云主机必须处于同一个VPC下，因此要先创建相同私有网络和子网的云主机，从该云主机下获取到“公网IP”，才能访问云搜索Elasticsearch服务。
### curl测试访问内网域名
1.ssh 用户名@公网IP，输入密码。</br>
2.通过Linux环境下的curl命令访问云搜索Elasticsearch实例的9200端口。指定账号密码访问示例格式为curl –XGET [实例内网访问域名]/_cat，内网访问域名为ES实例基本信息界面的**内网访问域名**，指令示例如下：
```
curl -XGET es-nlb-es-kgqo8zmgcv.jvessel-open-hb.jdcloud.com:9200/_cat
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
curl -H 'Content-Type: application/x-ndjson' -XPOST 'es-nlb-es-u92rc1eulw.jvessel-open-hb.jdcloud.com:9200/bank/account/_bulk?pretty' --data-binary @accounts.json
curl -X GET "es-nlb-es-u92rc1eulw.jvessel-open-hb.jdcloud.com:9200/_cat/indices?v
```
即数据成功加载到ES集群。


