# describeAllRegionAlarmsCm


## 描述
查询所有region的自定义监控规则

## 请求方式
GET

## 请求地址
https://monitor.jdcloud-api.com/v1/cm/alarms


## 请求参数
|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**enabled**|Long|False| |规则状态：1为启用，0为禁用|
|**isAlarming**|Long|False| |是否为正在报警的规则，0为忽略，1为是，与 status 同时只能生效一个,isAlarming 优先生效|
|**namespace**|String|False| |命名空间名称|
|**obj**|String|False| |对象名称|
|**pageNumber**|Long|False| |当前所在页，默认为1|
|**pageSize**|Long|False| |页面大小，默认为20；取值范围[1, 100]|
|**region**|String|False| |region info|
|**resourceId**|String|False| |资源Id|
|**serviceCode**|String|False| |产品名称|
|**status**|Long|False| |规则报警状态, 1：正常, 2：报警，4：数据不足|


## 返回参数
|名称|类型|描述|
|---|---|---|
|**requestId**|String|请求的标识id|
|**result**|Result| |

### Result
|名称|类型|描述|
|---|---|---|
|**alarmList**|CmAlarm[]|规则列表|
|**numberPages**|Long|总页数|
|**numberRecords**|Long|总记录数|
|**pageNumber**|Long|当前页码|
|**pageSize**|Long|分页大小|
### CmAlarm
|名称|类型|描述|
|---|---|---|
|**calculation**|String|统计方法：平均值=avg、最大值=max、最小值=min|
|**contactGroups**|String[]| |
|**contactPersons**|String[]| |
|**createTime**|String| |
|**enabled**|Long|启用禁用 1启用，0禁用|
|**id**|String|规则id|
|**metric**|String|监控项|
|**metricName**|String|规则id监控项名称|
|**namespace**|String|命名空间|
|**namespaceUID**|String|命名空间id|
|**noticePeriod**|Long|通知周期 单位：小时|
|**noticeTime**|String| |
|**obj**|String|对象|
|**objUID**|String|对象id|
|**operation**|String|>=、>、<、<=、=、！=|
|**period**|Long|统计周期（单位：分钟）|
|**region**|String|地域信息|
|**resourceId**|String|此规则所应用的资源id|
|**rootRuleId**|Long|root rule id|
|**ruleId**|Long|rule id|
|**serviceCode**|String|报警规则对应的产品|
|**status**|Long|监控项状态:1正常，2告警，4数据不足|
|**tag**|String|监控项附属信息|
|**threshold**|Double|阈值|
|**times**|Long|连续多少次后报警|
|**value**|Double|报警值|

## 返回码
|返回码|描述|
|---|---|
|**200**|查询规则|
