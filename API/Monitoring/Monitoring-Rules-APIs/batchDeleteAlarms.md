# batchDeleteAlarms


## 描述
批量删除规则

## 请求方式
DELETE

## 请求地址
https://monitor.jcloud.com/v1/regions/{regionId}/alarms

|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**regionId**|String|True| |地域 Id|

## 请求参数
|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**filter**|Filter[]|True| |filter name为'ids'为要删除的告警id|

### Filter
|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**name**|String|False| | |
|**values**|String[]|False| | |

## 返回参数
|名称|类型|描述|
|---|---|---|
|**requestId**|String|请求的标识id|


## 返回码
|返回码|描述|
|---|---|
|**200**|OK|
