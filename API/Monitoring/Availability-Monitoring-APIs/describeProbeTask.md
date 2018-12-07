# describeProbeTask


## 描述
查询可用性监控任务

## 请求方式
GET

## 请求地址
https://monitor.jdcloud-api.com/v1/am/probeTask/{probeTaskID}

|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**probeTaskID**|String|True| |探测任务的task_id|

## 请求参数
无


## 返回参数
|名称|类型|描述|
|---|---|---|
|**requestId**|String|请求的标识id|
|**result**|Result| |

### Result
|名称|类型|描述|
|---|---|---|
|**address**|String|探测地址|
|**createTime**|String|创建时间|
|**deleted**|Boolean|是否被删除|
|**enable**|Boolean|是否启用|
|**frequency**|Long|探测频率，单位秒|
|**httpBody**|String|http探测的body|
|**httpCookie**|KeyValue[]|http探测的cookie|
|**httpHeader**|KeyValue[]|http探测的header|
|**httpType**|Long|http探测方式|
|**name**|String|探测任务 名称|
|**pin**|String|pin|
|**port**|Long|探测端口|
|**probeType**|Long|探测类型1:http、2:telnet|
|**probes**|Probe[]|探测源信息|
|**targetId**|String|探测对象的uid(http探测方法无uid)|
|**targetRegion**|String|探测对象所在region，redis或RDS所在region|
|**taskId**|String|探测任务 id|
|**taskType**|Long|任务类型、1:url/ip、2:RDS、3:redis|
|**timeout**|Long|探测超时时间，单位秒|
|**updateTime**|String|更新时间|
### Probe
|名称|类型|描述|
|---|---|---|
|**privateIp**|String|探测源所在云主机内网ip|
|**publicIp**|String|探测源所在云主机公网ip|
|**region**|String|探测源所在region|
|**uuid**|String|探测源所在云主机的uuid|
### KeyValue
|名称|类型|描述|
|---|---|---|
|**key**|String|key|
|**value**|String|value|

## 返回码
|返回码|描述|
|---|---|
|**200**|查询指定可用性监控任务|
