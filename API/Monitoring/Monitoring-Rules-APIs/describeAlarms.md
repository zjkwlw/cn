# describeAlarms


## 描述
查询规则, 查询参数组合及优先级从高到低为：
1：serviceCode不为空
1.1：serviceCode + resourceId
1.2: serviceCode + resourceIds
2：serviceCodes不为空
3: 所有规则

## 请求方式
GET

## 请求地址
https://monitor.jcloud.com/v1/regions/{regionId}/alarms

|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**regionId**|String|True| |地域 Id|

## 请求参数
|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**alarmId**|String|False| |规则的id|
|**enabled**|Integer|False| |规则状态：1为启用，0为禁用|
|**filters**|Filter[]|False| |服务码或资源Id列表<br>filter name 为serviceCodes表示查询多个产品线的规则<br>filter name 为resourceIds表示查询多个资源的规则|
|**isAlarming**|Integer|False| |是否为正在报警的规则，0为忽略，1为是，与 status 同时只能生效一个,isAlarming 优先生效|
|**pageNumber**|Integer|False| |当前所在页，默认为1|
|**pageSize**|Integer|False| |页面大小，默认为20；取值范围[1, 100]|
|**resourceID**|String|False| |资源ID|
|**ruleType**|Integer|False| |规则类型, 1表示资源监控，6表示站点监控|
|**serviceCode**|String|False| |产品名称|
|**status**|Integer|False| |规则报警状态, 1：正常, 2：报警，4：数据不足|

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
|**alarmList**|DescribedAlarm[]|规则列表|
|**total**|Integer|规则总数|
### DescribedAlarm
|名称|类型|描述|
|---|---|---|
|**calculateUnit**|String|计算单位|
|**calculation**|String|统计方法：平均值=avg、最大值=max、最小值=min|
|**createTime**|String|创建时间|
|**downSample**|String|降采样方法|
|**enabled**|Integer|是否启用|
|**id**|String|报警规则ID|
|**metric**|String|监控项|
|**metricName**|String|监控项名称|
|**noticeLevel**|NoticeLevel| |
|**noticePeriod**|Integer|告警周期|
|**operation**|String|gt, gte, lt, lte, eq, ne|
|**period**|Integer|统计周期（单位：分钟）|
|**region**|String|地域信息|
|**resourceId**|String|资源id|
|**serviceCode**|String|产品线编码|
|**status**|Integer|监控项状态：1正常，2告警，4数据不足|
|**tags**|Object|标签|
|**threshold**|Number|告警阈值|
|**times**|Integer|告警次数|
### NoticeLevel
|名称|类型|描述|
|---|---|---|
|**custom**|Boolean|是否为用户自己定义的级别，自定义(true) or 固定(false)|
|**levels**|Object|报警级别以及对应的指标，common：一般 critial： 严重 fatal：紧急|

## 返回码
|返回码|描述|
|---|---|
|**200**|查询监控规则结果|
