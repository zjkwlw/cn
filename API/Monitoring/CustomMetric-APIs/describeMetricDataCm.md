# describeMetricDataCm


## 描述
查询自定义监控的metric数据

## 请求方式
POST

## 请求地址
https://monitor.jdcloud-api.com/v1/regions/{regionId}/cm/namespaces/{namespaceUID}/objs/{objUID}/metricData

|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**namespaceUID**|String|True| |region|
|**objUID**|String|True| |region|
|**regionId**|String|True| |region|

## 请求参数
|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**aggrType**|String|False| | |
|**endTime**|String|False| |查询时间范围的结束时间， UTC时间，格式：2016-12- yyyy-MM-dd'T'HH:mm:ssZ（为空时，将由startTime与timeInterval计算得出）<br>in: query|
|**metricUID**|String[]|False| |metric id列表<br>in: query|
|**startTime**|String|False| |查询时间范围的开始时间， UTC时间，格式：yyyy-MM-dd'T'HH:mm:ssZ（默认为当前时间，早于30d时，将被重置为30d）<br>in: query|
|**timeInterval**|String|False| |时间间隔：1h，6h，12h，1d，3d，7d，14d，固定时间间隔，timeInterval 与 endTime 至少填一项<br>in: query|


## 返回参数
|名称|类型|描述|
|---|---|---|
|**requestId**|String| |
|**result**|Result| |

### Result
|名称|类型|描述|
|---|---|---|
|**metricDatas**|MetricDataItemCm[]| |
### MetricDataItemCm
|名称|类型|描述|
|---|---|---|
|**data**|DataPoint[]| |
|**metric**|MetricCm| |
### DataPoint
|名称|类型|描述|
|---|---|---|
|**timestamp**|Long| |
|**value**|Object| |
### MetricCm
|名称|类型|描述|
|---|---|---|
|**aggrPeriod**|Long| |
|**aggrType**|String| |
|**metricName**|String| |
|**metricUID**|String| |

## 返回码
|返回码|描述|
|---|---|
|**200**|api DescribeMetricDataCm Response|
