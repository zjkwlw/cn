# describeMetricsForCreateTemplate


## 描述
根据产品线查询查询可以创建模板的metric

## 请求方式
GET

## 请求地址
https://monitor.jdcloud-api.com/v1/metricsForCreateTemplate


## 请求参数
|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**serviceCode**|String|True| |资源的类型，取值vm, lb, ip, database 等|


## 返回参数
|名称|类型|描述|
|---|---|---|
|**requestId**|String|请求的标识id|
|**result**|Result| |

### Result
|名称|类型|描述|
|---|---|---|
|**metrics**|MetricInfo[]|metric列表|
### MetricInfo
|名称|类型|描述|
|---|---|---|
|**calculateUnit**|String|metric单位|
|**metric**|String|metric|
|**metricId**|Long|metricID|
|**metricName**|String|metric中文显示名称|
|**serviceCode**|String|资源的类型|

## 返回码
|返回码|描述|
|---|---|
|**200**|查询可以创建模板的metric|
