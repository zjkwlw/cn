# describeProbeHistory


## 描述
查询可用性监控任务的指定探测源的异常探测历史

## 请求方式
GET

## 请求地址
https://monitor.jdcloud-api.com/v1/am/probeTask/{probeTaskID}/probe/{probeID}

|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**probeID**|String|True| |探测源id，  id长度（0,50]|
|**probeTaskID**|String|True| |可用性监控task_id, id长度(0,50]|

## 请求参数
|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**endTime**|String|False| |查询时间范围的结束时间， UTC时间，格式：2016-12- yyyy-MM-dd'T'HH:mm:ssZ（为空时，默认为当前时间）|
|**startTime**|String|False| |查询时间范围的开始时间， UTC时间，格式：yyyy-MM-dd'T'HH:mm:ssZ（默认为当前时间往前三天，早于3d时，将被重置为3d）|


## 返回参数
|名称|类型|描述|
|---|---|---|
|**requestId**|String|请求的标识id|
|**result**|Result| |

### Result
|名称|类型|描述|
|---|---|---|
|**events**|Event[]|异常数据,当events为空时，Agent在当前查询时间段为无数据上报，Agent异常|
|**name**|String|探测源名称|
|**uuid**|String|探测源uuid|
### Event
|名称|类型|描述|
|---|---|---|
|**probeResult**|Long|探测结果 1:探测成功  2：探测失败  3：探测超时|
|**probeStatus**|Long|插件状态 1：正常  2：异常|
|**timestamp**|Long|时间戳|

## 返回码
|返回码|描述|
|---|---|
|**200**|查询可用性监控任务指定探测源的异常历史|
