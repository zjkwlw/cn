# describeAlarmingRules


## 描述
尚未恢复的告警查询接口

## 请求方式
GET

## 请求地址
https://monitor.jdcloud-api.com/v1/overview/queryAlarmingRules


## 请求参数
|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**datacenter**|String|False| |要查询的地域，为空则查询所有的|
|**filters**|Filter[]|False| |服务码列表<br>filter name 为serviceCodes表示查询多个产品线的规则|
|**pageNumber**|Long|False| |当前所在页，默认为1|
|**pageSize**|Long|False| |页面大小，默认为20；取值范围[1, 100]|

### Filter
|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**name**|String|False| | |
|**values**|String[]|False| | |

## 返回参数
|名称|类型|描述|
|---|---|---|
|**requestId**|String|请求的标识id|
|**result**|Result| |

### Result
|名称|类型|描述|
|---|---|---|
|**alarmHistoryList**|AlarmHistoryWithDetail[]|未恢复的报警|
|**numberPages**|Long|总页数|
|**numberRecords**|Long|总记录数|
|**pageNumber**|Long|当前页码|
|**pageSize**|Long|分页大小|
### AlarmHistoryWithDetail
|名称|类型|描述|
|---|---|---|
|**contacts**|DescribedNoticeContacts[]|告警联系人|
|**noticeLevel**|String|用于前端显示的‘触发告警级别’。从低到高分别为‘普通’, ‘紧急’, ‘严重’|
|**noticeTime**|Long|noticeTime|
|**rule**|Rule| |
|**value**|Double|告警值|
### DescribedNoticeContacts
|名称|类型|描述|
|---|---|---|
|**referenceId**|Long|联系人ID|
|**referenceType**|Long|联系人类型。 0 - 联系人分组id， 1 - 联系人id|
### Rule
|名称|类型|描述|
|---|---|---|
|**autoScalingPolicyId**|String|AutoScalingPolicyID|
|**calculateUnit**|String|calculateUnit|
|**calculation**|String|calculation|
|**createTime**|String|createTime|
|**dataMeaning**|Long|dataMeaning|
|**datacenter**|String|地域|
|**deleted**|Long|deleted|
|**downSample**|String|downSample|
|**enableTime**|String|enableTime|
|**enabled**|Long|enabled|
|**id**|String|uuid|
|**idpk**|Long| |
|**isLatest**|Long|isLatest|
|**metric**|String|metric|
|**metricId**|Long|metricId|
|**metricName**|String|metricName|
|**noticeLevel**|NoticeLevel| |
|**noticePeriod**|Long|notice_period|
|**operation**|String|operation|
|**period**|Long|period|
|**pin**|String|pin|
|**preVersionId**|Long|preVersionId|
|**region**|String|region|
|**resourceId**|String|资源 id|
|**rootRuleId**|Long|rootRuleID|
|**ruleType**|Long|rutye 1:经典监控  5：自定义监控   6：站点监控 7：可用性监控|
|**serviceCode**|String|serviceCode|
|**status**|Long|status|
|**statusTime**|String|statusTime|
|**tags**|Object|tags|
|**tagsNonGrouping**|String|tagsNonGrouping|
|**threshold**|Double|threshold|
|**times**|Long|times|
|**updateTime**|String|updateTime|
|**version**|Long|version|
### NoticeLevel
|名称|类型|描述|
|---|---|---|
|**custom**|Boolean|是否为用户自己定义的级别，自定义(true) or 固定(false)|
|**levels**|Object|报警级别以及对应的指标，common：一般 critial： 严重 fatal：紧急|

## 返回码
|返回码|描述|
|---|---|
|**200**|查询概览页尚未恢复的告警规则 统计|
