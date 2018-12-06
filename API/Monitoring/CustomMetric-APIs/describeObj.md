# describeObj


## 描述
查询obj

## 请求方式
GET

## 请求地址
https://monitor.jdcloud-api.com/v1/regions/{regionId}/cm/namespaces/{namespaceUID}/objs/{objUID}

|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**namespaceUID**|String|True| |namespaceUID|
|**objUID**|String|True| |objUID|
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
|**namespaceName**|String|命名空间名称|
|**objName**|String|obj名称|

## 返回码
|返回码|描述|
|---|---|
|**200**|查询对象|
