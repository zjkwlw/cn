# lastDownsample


## 描述
查看某资源的最后一个点

## 请求方式
GET

## 请求地址
https://monitor.jcloud.com/v1/regions/{regionId}/metrics/{metric}/lastDownsample

|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**metric**|String|True| |监控项英文标识(id)|
|**regionId**|String|True| |地域 Id|

## 请求参数
|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**aggrType**|String|False| |聚合方式：max avg min等|
|**endTime**|String|False| |查询时间范围的结束时间， UTC时间，格式：2016-12- yyyy-MM-dd'T'HH:mm:ssZ（为空时，将由startTime与timeInterval计算得出）|
|**resourceId**|String|True| |资源的uuid|
|**serviceCode**|String|True| |资源的类型，取值vm, lb, ip, database 等|
|**startTime**|String|False| |查询时间范围的开始时间， UTC时间，格式：yyyy-MM-dd'T'HH:mm:ssZ（默认为当前时间，早于30d时，将被重置为30d）|
|**tags**|TagFilter[]|False| |自定义标签|
|**timeInterval**|String|False| |查询的时间间隔，仅支持分钟级别，例如：1m|

### TagFilter
|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**key**|String|False| |Tag键|
|**values**|String[]|False| |Tag值|

## 返回参数
|名称|类型|描述|
|---|---|---|
|**requestId**|String|请求的标识id|
|**result**|Result| |

### Result
|名称|类型|描述|
|---|---|---|
|**items**|LastDownsampleRespItem[]| |
### LastDownsampleRespItem
|名称|类型|描述|
|---|---|---|
|**metric**|String| |
|**name**|String| |
|**value**|Object| |

## 返回码
|返回码|描述|
|---|---|
|**200**|查看某资源的最后一个点|
