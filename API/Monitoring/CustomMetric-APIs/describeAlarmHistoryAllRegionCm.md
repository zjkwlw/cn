# describeAlarmHistoryAllRegionCm


## 描述
查询自定义监控所有region规则告警历史

## 请求方式
GET

## 请求地址
https://monitor.jdcloud-api.com/v1/cm/alarmHistory


## 请求参数
|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**endTime**|String|True| |查询数据结束时间，默认当前时间，可以输入long型时间，也可以输入yyyy-MM-dd'T'HH:mm:ssZ类型时间|
|**id**|Long|False| |报警规则的Id|
|**namespace**|String|False| |namespace|
|**obi**|String|False| |obj|
|**pageNumber**|Long|False| |当前所在页，默认为1|
|**pageSize**|Long|False| |页面大小，默认为20；取值范围[1, 100]|
|**resourceId**|String|False| |资源Id|
|**serviceCode**|String|False| |产品名称|
|**startTime**|String|True| |查询数据开始时间，默认24小时前，可以输入long型时间，也可以输入yyyy-MM-dd'T'HH:mm:ssZ类型时间|


## 返回参数
|名称|类型|描述|
|---|---|---|
|**requestId**|String|请求的标识id|
|**result**|Result| |

### Result
|名称|类型|描述|
|---|---|---|
|**alarmHistoryList**|CmAlarmHistory[]|报警历史列表|
|**numberPages**|Long|总页数|
|**numberRecords**|Long|总记录数|
|**pageNumber**|Long|当前页码|
|**pageSize**|Long|分页大小|
### CmAlarmHistory
|名称|类型|描述|
|---|---|---|
|**calculation**|String|统计方法：平均值=avg、最大值=max、最小值=min|
|**contactGroups**|String[]| |
|**contactPersons**|String[]| |
|**deleted**|Long|该规则是否已经被删除，1表示已经被删除，0表示未删除，被删除的规则，在使用查询规则的接口时，将不会被检索到|
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
|**tag**|String|监控项附属信息|
|**threshold**|Double|阈值|
|**times**|Long|连续多少次后报警|
|**value**|Double|报警值|

## 返回码
|返回码|描述|
|---|---|
|**200**|查询自定义监控规则告警历史|
