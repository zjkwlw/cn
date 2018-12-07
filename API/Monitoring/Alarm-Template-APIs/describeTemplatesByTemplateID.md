# describeTemplatesByTemplateID


## 描述
根据模板ID查询报警模板

## 请求方式
GET

## 请求地址
https://monitor.jdcloud-api.com/v1/template/{templateId}

|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**templateId**|String|True| |模板 id|

## 请求参数
|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**templateType**|Long|False| |模板类型，区分默认模板和用户自定义模板：1表示默认模板，2表示用户自定义模板<br>in: query|


## 返回参数
|名称|类型|描述|
|---|---|---|
|**requestId**|String|请求的标识id|
|**result**|Result| |

### Result
|名称|类型|描述|
|---|---|---|
|**template**|TemplateVo| |
### TemplateVo
|名称|类型|描述|
|---|---|---|
|**createTime**|String| |
|**description**|String|模板描述|
|**pin**|String|用户|
|**rulesCount**|Long|模板内包含的规则数量|
|**serviceCode**|String|模板所属资源类型|
|**templateId**|Long|模板id|
|**templateName**|String|模板名称|
|**templateRules**|AlarmVo[]|模板内包含的规则|
|**templateRulesString**|String[]|模板内包含的提供给前端的拼接好的规则|
|**templateType**|Long|模板类型，区分默认模板和用户自定义模板：1表示默认模板，2表示用户自定义模板|
|**updateTime**|String| |
### AlarmVo
|名称|类型|描述|
|---|---|---|
|**calculateUnit**|String|监控项单位|
|**calculation**|String|统计方法：平均值=avg、最大值=max、最小值=min|
|**contacts**|BaseContact[]|联系人列表|
|**createTime**|String| |
|**deleted**|Long|是否删除 1正常，0删除|
|**id**|Long|规则ID|
|**metricId**|Long|监控项ID|
|**metricName**|String|监控项名称|
|**noticeLevel**|NoticeLevel| |
|**noticePeriod**|Long|通知周期|
|**operation**|String|报警比较符，只能为以下几种lte(<=),lt(<),gt(>),gte(>=),eq(==),ne(!=)|
|**period**|Long|统计周期（单位：分钟）|
|**ruleType**|Long|规则类型|
|**serviceCode**|String|规则所属资源类型|
|**tag**|String|监控项附属信息|
|**tags**|Object|多值标签|
|**threshold**|Double|阈值|
|**times**|Long|连续多少次后报警|
|**updateTime**|String| |
### BaseContact
|名称|类型|描述|
|---|---|---|
|**referenceId**|Long|联系人id|
|**referenceType**|Long|联系人id类型：0,联系人分组id;1,联系人id|
### NoticeLevel
|名称|类型|描述|
|---|---|---|
|**custom**|Boolean|是否为用户自己定义的级别，自定义(true) or 固定(false)|
|**levels**|Object|报警级别以及对应的指标，common：一般 critial： 严重 fatal：紧急|

## 返回码
|返回码|描述|
|---|---|
|**200**|根据模板ID查询报警模板|
