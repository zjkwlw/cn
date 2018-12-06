# createTemplate


## 描述
创建自定义报警模板

## 请求方式
POST

## 请求地址
https://monitor.jdcloud-api.com/v1/template


## 请求参数
|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**clientToken**|String|True| |幂等性校验参数,最长36位|
|**description**|String|False| |模板描述|
|**ruleServiceCode**|String|True| |规则的资源类型|
|**serviceCode**|String|True| |模板的资源类型|
|**templateName**|String|True| |模板名称,长度1-32个字符，只允许中英文、数字、''-''和"_"|
|**templateRules**|BaseRuleT[]|True| |模板内包含的规则|

### BaseRuleT
|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**autoScalingPolicyId**|String|False| |弹性伸缩组ID|
|**calculateUnit**|String|False| |监控项单位|
|**calculation**|String|True| |统计方法，必须与定义的metric一致，可选值列表：avg,sum,max,min|
|**downSample**|String|False| |降采样函数|
|**metricId**|Long|True| |监控项ID|
|**noticeLevel**|NoticeLevel|False| | |
|**noticePeriod**|Long|True| |通知周期，单位：小时|
|**operation**|String|True| |报警比较符，只能为以下几种lte(<=),lt(<),gt(>),gte(>=),eq(==),ne(!=)|
|**period**|Long|True| |查询指标的周期，单位为分钟,目前支持的取值：1, 2，5，15，30，60|
|**ruleType**|Long|True| |规则类型, 1表示云监控，2表示弹性伸缩，3表示AG，4表示AutoHeal，5表示自定义监控，6表示hawkeye|
|**tags**|Object|False| |多值标签|
|**threshold**|Double|True| |报警阈值，目前只开放数值类型功能|
|**times**|Long|True| |连续探测几次都满足阈值条件时报警，可选值:1,2,3,5,10,15,30,60|
### NoticeLevel
|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**custom**|Boolean|True| |是否为用户自己定义的级别，自定义(true) or 固定(false)|
|**levels**|Object|True| |报警级别以及对应的指标，common：一般 critial： 严重 fatal：紧急|

## 返回参数
|名称|类型|描述|
|---|---|---|
|**requestId**|String|请求的标识id|
|**result**|Result| |

### Result
|名称|类型|描述|
|---|---|---|
|**success**|Boolean|是否创建成功|
|**templateId**|Long|创建成功的模板id|

## 返回码
|返回码|描述|
|---|---|
|**200**|创建自定义报警模板|
