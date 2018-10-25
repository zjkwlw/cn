# batchDisableAlarms


## 描述
批量禁用规则

## 请求方式
POST

## 请求地址
https://monitor.jcloud.com/v1/regions/{regionId}/alarms:disable

|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**regionId**|String|True| |地域 Id|

## 请求参数
|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**ids**|String[]|True| |告警规则的ID列表|


## 返回参数
|名称|类型|描述|
|---|---|---|
|**requestId**|String|请求的标识id|


## 返回码
|返回码|描述|
|---|---|
|**200**|OK|
