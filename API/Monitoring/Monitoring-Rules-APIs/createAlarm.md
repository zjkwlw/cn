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
|**contactGroups**|String[]|False| |报警规则通知的联系组，必须在控制台上已创建，例如" ['联系组1','联系组2']"|
|**contactPersons**|String[]|False| |报警规则通知的联系人，必须在控制台上已创建，例如 [“联系人1”,”联系人2”]|
|**downSample**|String|False| |取样频次|
|**metric**|String|True| |根据产品线查询可用监控项列表 接口 返回的Metric字段|
|**noticePeriod**|Integer|False| |通知周期 单位：小时|
|**resourceIds**|String[]|True| |报警规则对应实例列表，每次最多100个，例如"['resourceId1','resourceId2']"|
|**serviceCode**|String|True| |产品名称|
|**threshold**|Number|True| |查询指标的周期，单位为分钟,目前支持的取值：2，5，15，30，60|
|**times**|Integer|True| |连续探测几次都满足阈值条件时报警，可选值:1,2,3,5|


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
