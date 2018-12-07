# applyTemplate


## 描述
应用报警模板到资源

## 请求方式
POST

## 请求地址
https://monitor.jdcloud-api.com/v1/template/{templateId}/resources

|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**templateId**|String|True| |模板 id|

## 请求参数
|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**clientToken**|String|True| |幂等性校验参数,最长36位|
|**contacts**|BaseContact[]|False| |联系人列表|
|**dataCenters**|String[]|True| |dataCenters，该资源所处地域，与resourceIds一一对应|
|**resourceIds**|String[]|True| |资源ID列表，resourceIds数量为1--40，每一项不能为空或包含*|
|**serviceCode**|String|True| |资源类型|
|**tagsArray**|Object[]|False| |标签组，模板下面规则对应的tags，与resourceIds一一对应|
|**templateType**|Long|True| |模板类型，1表示默认模板，2表示用户自定义模板|
|**webHookContent**|String|False| |回调content 注:仅webHookUrl和webHookContent均不为空时,才会创建webHook|
|**webHookProtocol**|String|False| |webHook协议,https或http 注:此处需和webHookUrl相匹配|
|**webHookSecret**|String|False| |回调secret,用户请求签名,防伪造|
|**webHookUrl**|String|False| |回调url|

### BaseContact
|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**referenceId**|Long|True| |联系人id|
|**referenceType**|Long|True| |联系人id类型：0,联系人分组id;1,联系人id|

## 返回参数
|名称|类型|描述|
|---|---|---|
|**requestId**|String|请求的标识id|
|**result**|Result| |

### Result
|名称|类型|描述|
|---|---|---|
|**ruleIds**|Long[]|创建成功的规则id列表|
|**success**|Boolean|是否创建成功|

## 返回码
|返回码|描述|
|---|---|
|**200**|应用报警模板到资源|
