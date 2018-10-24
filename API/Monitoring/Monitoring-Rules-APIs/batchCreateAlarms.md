# batchCreateAlarms


## 描述
批量创建报警规则，可以为多个实例创建多个报警规则。

## 请求方式
POST

## 请求地址
https://monitor.jcloud.com/v1/regions/{regionId}/alarms/batch

|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**regionId**|String|True| |地域 Id|

## 请求参数
|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**clientToken**|String|True| |幂等性校验参数，最长36位|
|**contacts**|BaseContact[]|False| |通知的联系人|
|**datacenter**|String|False| |地域|
|**resourceIds**|String[]|True| |报警规则对应实例列表，每次最多100个，例如"['resourceId1','resourceId2']"|
|**ruleType**|Integer|False| |规则类型, 1表示资源监控，6表示站点监控，默认为1|
|**rules**|BaseRule[]|True| |要批量创建的规则列表|
|**saveTemplate**|Boolean|False| |是否保存为模板|
|**serviceCode**|String|True| |产品线标识，规则对应的serviceCode|
|**templateName**|String|False| |模板名称，保存模板时，不能为空|
|**templateServiceCode**|String|False| |产品线标识，保存为模板时，模板对应的serviceCode|
|**webHookContent**|String|False| |回调content 注：仅webHookUrl和webHookContent均不为空时，才会创建webHook|
|**webHookProtocol**|String|False| |webHook协议|
|**webHookSecret**|String|False| |回调secret，用户请求签名，防伪造|
|**webHookUrl**|String|False| |回调url|

### BaseContact
|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**referenceId**|Integer|True| |联系人id|
|**referenceType**|Integer|True| |联系人id类型：0,联系人分组id;1,联系人id|
### BaseRule
|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**autoScalingPolicyId**|String|False| |弹性伸缩组ID|
|**calculateUnit**|String|True| |单位|
|**calculation**|String|True| |统计方法，必须与定义的metric一致，可选值列表：avg,sum,max,min|
|**downSample**|String|True| |降采样函数|
|**metric**|String|True| |监控项|
|**noticeLevel**|NoticeLevel|False| | |
|**noticePeriod**|Integer|True| |通知周期，单位：小时|
|**operation**|String|True| |报警比较符，只能为以下几种lte(<=),lt(<),gt(>),gte(>=),eq(==),ne(!=)|
|**period**|Integer|True| |查询指标的周期，单位为分钟,目前支持的取值：1,2，5，15，30，60|
|**ruleType**|Integer|False| |规则类型, 1云监控的规则， 6站点监控。默认为1|
|**tags**|Object|False| |多值标签|
|**threshold**|Number|True| |报警阈值，目前只开放数值类型功能|
|**times**|Integer|True| |连续探测几次都满足阈值条件时报警，可选值:1,2,3,5,10,15,30,60|
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
|**alarmIDList**|String[]|创建成功的规则id列表|

## 返回码
|返回码|描述|
|---|---|
|**200**|批量创建规则|
