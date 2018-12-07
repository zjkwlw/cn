# describeNamespaces


## 描述
查询自定义监控命名空间列表

## 请求方式
GET

## 请求地址
https://monitor.jdcloud-api.com/v1/regions/{regionId}/cm/namespaces

|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**regionId**|String|True| |region|

## 请求参数
无


## 返回参数
|名称|类型|描述|
|---|---|---|
|**requestId**|String|请求的标识id|
|**result**|Result| |

### Result
|名称|类型|描述|
|---|---|---|
|**namespaceList**|NsInfo[]|命名空间列表|
### NsInfo
|名称|类型|描述|
|---|---|---|
|**metricCount**|Long|metric个数|
|**nsName**|String|命名空间名称|
|**nsUid**|String|命名空间uid|
|**objCount**|Long|obj个数|

## 返回码
|返回码|描述|
|---|---|
|**200**|查询命名空间|
