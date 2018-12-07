# describeObjsByNsUID


## 描述
查询obj列表

## 请求方式
GET

## 请求地址
https://monitor.jdcloud-api.com/v1/regions/{regionId}/cm/namespaces/{namespaceUID}/objs

|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**namespaceUID**|String|True| |namespaceUID|
|**regionId**|String|True| |region|

## 请求参数
|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**pageNumber**|Long|False| |当前所在页，默认为1|
|**pageSize**|Long|False| |页面大小，默认为20；取值范围[1, 100]|


## 返回参数
|名称|类型|描述|
|---|---|---|
|**requestId**|String|请求的标识id|
|**result**|Result| |

### Result
|名称|类型|描述|
|---|---|---|
|**numberPages**|Long|总页数|
|**numberRecords**|Long|总记录数|
|**objList**|ObjInfo[]|obj列表|
|**pageNumber**|Long|当前页码|
|**pageSize**|Long|分页大小|
### ObjInfo
|名称|类型|描述|
|---|---|---|
|**metrics**|String[]|metric列表|
|**objName**|String|obj名称|
|**objUid**|String|obj UID|

## 返回码
|返回码|描述|
|---|---|
|**200**|查询对象列表|
