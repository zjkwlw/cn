# describeRuleCounting


## 描述
概览页规则统计接口

## 请求方式
GET

## 请求地址
https://monitor.jdcloud-api.com/v1/overview/queryRuleCountings


## 请求参数
|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**adminPin**|String|False| |主帐号|
|**datacenter**|String|False| |要查询的地域，为空则查询所有的|
|**filters**|Filter[]|False| |服务码列表<br>filter name 为serviceCodes表示查询多个产品线的规则|
|**pin**|String|False| |pin|

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
|**alarmRuleCount**|Long|处于报警状态的规则个数  status:2|
|**disableRuleCount**|Long|未启用的规则 数量|
|**normalRuleCount**|Long|处于正常状态的规则个数  status：1|
|**serviceCodes**|String[]|报警联系人列表|
|**subUserPermission**|Boolean|默认为true，当使用主子帐号功能，且用户没有任何规则的权限时，为false|
|**totalRuleCount**|Long|监控规则 总数|
|**unknownRuleCount**|Long|处于数据不足状态的规则 个数  status:4|

## 返回码
|返回码|描述|
|---|---|
|**200**|查询概览页规则 统计|
