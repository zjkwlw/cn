# createAlarm


## 描述
创建报警规则，可以为某一个实例创建报警规则，也可以为多个实例同时创建报警规则。

## 请求方式
POST

## 请求地址
https://monitor.jcloud.com/v1/regions/{regionId}/alarms

|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**regionId**|String|True| |地域 Id|

## 请求参数
|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**clientToken**|String|True| |幂等性校验参数,最长36位|
|**createAlarmSpec**|CreateAlarmSpec|True| | |


## 返回参数
|名称|类型|描述|
|---|---|---|
|**requestId**|String|请求的标识id|
|**result**|Result| |

### Result
|名称|类型|描述|
|---|---|---|
|**alarmIdList**|String[]|创建成功的规则id列表|

## 返回码
|返回码|描述|
|---|---|
|**200**|创建规则|
