# deleteNamespace


## 描述
删除自定义监控命名空间

## 请求方式
DELETE

## 请求地址
https://monitor.jdcloud-api.com/v1/regions/{regionId}/cm/namespaces/{namespaceUID}

|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**namespaceUID**|String|True| |namespaceUID|
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
|**result**|Boolean|是否成功|

## 返回码
|返回码|描述|
|---|---|
|**200**|删除命名空间|
