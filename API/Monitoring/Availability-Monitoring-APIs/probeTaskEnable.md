# probeTaskEnable


## 描述
启用、禁用可用性监控任务

## 请求方式
POST

## 请求地址
https://monitor.jdcloud-api.com/v1/am/probeTask/enable


## 请求参数
|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**enabled**|Boolean|False| |默认：禁用； true：启用，false：禁用|
|**taskId**|String[]|True| |要启用或禁用的探测任务的task_id列表，列表长度[1，100)|


## 返回参数
|名称|类型|描述|
|---|---|---|
|**requestId**|String|请求的标识id|
|**result**|Result| |

### Result
|名称|类型|描述|
|---|---|---|
|**suc**|Boolean|可用性监控任务 【启用｜禁用】 是否成功|

## 返回码
|返回码|描述|
|---|---|
|**200**|启用、禁用可用性监控任务|
