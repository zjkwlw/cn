# deleteTemplates


## 描述
批量删除自定义报警模板

## 请求方式
DELETE

## 请求地址
https://monitor.jdcloud-api.com/v1/template


## 请求参数
|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**templateIds**|String|True| |模板Id,多个templateId用|分隔|


## 返回参数
|名称|类型|描述|
|---|---|---|
|**requestId**|String|请求的标识id|
|**result**|Result| |

### Result
|名称|类型|描述|
|---|---|---|
|**success**|Boolean|是否删除成功|

## 返回码
|返回码|描述|
|---|---|
|**200**|删除自定义报警模板|
