# describeProbeTasks


## 描述
查询可用性监控任务列表

## 请求方式
GET

## 请求地址
https://monitor.jdcloud-api.com/v1/am/probeTask


## 请求参数
|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**name**|String|False| |根据探测任务的名称查询，支持模糊查询|
|**pageNumber**|Long|False| |当前所在页，默认为1|
|**pageSize**|Long|False| |页面大小，默认为20；取值范围[1, 100]|
|**type**|Long|False| |根据探测任务的类型查询，1、http 2、telnet|


## 返回参数
|名称|类型|描述|
|---|---|---|
|**requestId**|String|请求的标识id|
|**result**|Result| |

### Result
|名称|类型|描述|
|---|---|---|
|**numberPages**|Long|总页数|
|**numberRecords**|Long|总记录数|
|**pageNumber**|Long|当前页码|
|**pageSize**|Long|分页大小|
|**taskInfo**|TaskInfo[]|task信息|
|**totalCount**|Long|总task个数|
### TaskInfo
|名称|类型|描述|
|---|---|---|
|**abnormalCount**|Long|探测异常数  ，null代表缺值。只统计探测失败，超时的个数。|
|**address**|String|task的探测地址|
|**enabled**|Boolean|任务状态[false：己禁用，true：己启用]|
|**name**|String|task名称|
|**probeAvailability**|Double|task的可用率|
|**probeCount**|Long|该task的探测源个数|
|**probeType**|Long|task的探测类型，1：http，2：telnet|
|**responseTime**|Double|task的探测平均响应时间|
|**taskId**|String|task的id|

## 返回码
|返回码|描述|
|---|---|
|**200**|查询可用性监控任务列表|
