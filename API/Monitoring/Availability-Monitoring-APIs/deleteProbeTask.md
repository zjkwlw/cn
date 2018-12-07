# deleteProbeTask


## 描述
删除可用性监控任务

## 请求方式
DELETE

## 请求地址
https://monitor.jdcloud-api.com/v1/am/probeTask


## 请求参数
|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**probeTaskIDs**|String|True| |探测任务的task_id,多个taskId用|分隔|


## 返回参数
|名称|类型|描述|
|---|---|---|
|**requestId**|String|请求的标识id|
|**result**|Result| |

### Result
|名称|类型|描述|
|---|---|---|
|**suc**|Boolean|可用性监控任务是否删除成功|

## 返回码
|返回码|描述|
|---|---|
|**200**|删除可用性监控任务|
