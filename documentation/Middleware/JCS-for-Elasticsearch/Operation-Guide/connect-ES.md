## 访问ES
### 基于云服务器访问前提
京东云搜索Elasticsearch与依赖的云主机必须处于同一个VPC下，因此要先创建相同私有网络和子网的云主机，从该云主机下获取到“公网IP”，才能访问云搜索Elasticsearch服务。
### curl测试
通过Linux环境下的curl命令访问云搜索Elasticsearch实例的9200端口。
指定账号密码访问示例格式为curl –XGET [公网域名]，例如：
```
curl -XGET es-nlb-es-kgqo8zmgcv.jvessel-open-hb.jdcloud.com:9200
```
响应如下：
```
{
  "name" : "node-0",
  "cluster_name" : "es",
  "cluster_uuid" : "0GPfrABGTqqw8feSVq53Kw",
  "version" : {
    "number" : "5.6.9",
    "build_hash" : "877a590",
    "build_date" : "2018-04-12T16:25:14.838Z",
    "build_snapshot" : false,
    "lucene_version" : "6.6.1"
  },
  "tagline" : "You Know, for Search"
}
```
