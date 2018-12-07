# describeTopNSlowSql


## 描述
查看sqlserver数据库某资源一段时间内的topN慢sql数据

## 请求方式
GET

## 请求地址
https://monitor.jdcloud-api.com/v1/regions/{regionId}/topNSql

|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**regionId**|String|True| |region|

## 请求参数
|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**endTime**|String|False| |查询时间范围的结束时间， UTC时间，格式：2016-12- yyyy-MM-dd'T'HH:mm:ssZ（为空时，将由startTime与timeInterval计算得出）<br>in: query|
|**resourceId**|String|True| |资源的uuid|
|**serviceCode**|String|True| |资源的类型,sqlserver|
|**startTime**|String|False| |查询时间范围的开始时间， UTC时间，格式：yyyy-MM-dd'T'HH:mm:ssZ（默认为当前时间，早于30d时，将被重置为30d）<br>in: query|
|**timeInterval**|String|False| |时间间隔：1h，6h，12h，1d，3d，7d，14d，固定时间间隔，timeInterval 与 endTime 至少填一项<br>in: query|
|**topN**|Long|True| |topN数量|


## 返回参数
|名称|类型|描述|
|---|---|---|
|**requestId**|String|请求的标识id|
|**result**|Result| |

### Result
|名称|类型|描述|
|---|---|---|
|**topNsql**|SqlInfo[]|TopN慢sql数据|
### SqlInfo
|名称|类型|描述|
|---|---|---|
|**appCode**|String|产品标识，目前统一用jcloud|
|**client_net_address**|String|客户端IP地址|
|**database**|String|库名|
|**execution_time**|Long|SQL已执行时间（单位s）|
|**loginname**|String|用户名|
|**metric**|String|监控项|
|**region**|String|资源所在的地域|
|**resourceId**|String|资源的uuid|
|**serviceCode**|String|资源的类型|
|**session_id**|String|会话ID|
|**sqlstr**|String|SQL详细文本|
|**start_time**|String|SQL开始执行的时间|
|**status**|String|SQL会话请求状态|
|**time**|Long|毫秒级时间戳|
|**value**|Long|上报的监控值|

## 返回码
|返回码|描述|
|---|---|
|**200**|查看sqlserver数据库某资源一段时间内的topN慢sql数据|
