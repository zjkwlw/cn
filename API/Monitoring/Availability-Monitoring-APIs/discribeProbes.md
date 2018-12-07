# discribeProbes


## 描述
查询 可用性监控任务的探测源列表

## 请求方式
GET

## 请求地址
https://monitor.jdcloud-api.com/v1/am/probeTask/{probeTaskID}/probeList

|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**probeTaskID**|String|True| |探测任务的task_id|

## 请求参数
|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**filters**|Filter[]|False| |自定义标签|

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
|**probeList**|ProbeInfo[]| |
### ProbeInfo
|名称|类型|描述|
|---|---|---|
|**name**|String|探测源的所在主机名称|
|**privateIp**|String|探测源的内网ip|
|**probeResult**|Long|探测结果,缺点返回null,对应前端显示 "--" ,1:探测正常，2：探测失败，3：探测超时|
|**probeStatus**|Long|插件状态，  1：正常，2：异常|
|**publicIp**|String|探测源的公网ip|
|**targetStatus**|Long|探测目标状态，1：正常，2：异常(探测失败、探测超时)，缺点返回null,对应前端显示 "--"|
|**uuid**|String|探测源主机的uuid|
|**vmStatus**|String|云主机状态，对应云主机的状态,当找不到云主机，状态为"unExist"|

## 返回码
|返回码|描述|
|---|---|
|**200**|查询可用性监控任务的探测源列表|
