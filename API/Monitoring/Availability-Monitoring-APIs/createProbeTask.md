# createProbeTask


## 描述
创建可用性监控任务

## 请求方式
POST

## 请求地址
https://monitor.jdcloud-api.com/v1/am/probeTask


## 请求参数
|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**clientToken**|String|True| |幂等性校验参数,最长36位|
|**createProbeTaskSpec**|CreateProbeTaskParam|True| | |

### CreateProbeTaskParam
|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**address**|String|True| |探测地址，探测类型为http：内容为url（校验http或https头）；探测类型为telnet：内容为ip或域名（只允许中英文 、数字、中划线（-）、小数点（.）、开头及结尾均不能含有“-”）|
|**frequency**|Long|False| |探测间隔（单位：秒）：默认值：300，取值范围[60,1200]|
|**httpBody**|String|False| |http body：选择探测类型为1=http时有效，最长不超过1024字节<br>in: query|
|**httpCookie**|KeyValue[]|False| |http cookie：选择探测类型为1=http时有效，最大允许20个key、value对，最长不超过1024字节|
|**httpHeader**|KeyValue[]|False| |http header：选择探测类型为1=http时有效，最大允许20个key、value对，最长不超过1024字节|
|**httpType**|Long|False| |http探测方法：选择探测类型为1=http时有效，默认值为1=get，可选值：1:get、2:post、3:head|
|**name**|String|True| |task名称，不允许重复，长度不超过32字符，只允许中英文、数字、下划线_、中划线-, [0-9][a-z] [A-Z] [- _ ]|
|**port**|Long|False| |探测端口，探测类型为telnet时必填，取值范围 [1-65535]，http类型忽略该参数<br>in: query|
|**probeType**|Long|True| |探测类型：1=http、2=telnet|
|**probes**|Probe[]|True| |探测源（发起对探测目标探测的云主机，需安装相应的agent才能探测）|
|**targetId**|String|False| |探测目标id：该探测对象的uuid，任务类型为2：rds、3：redis时必填，|
|**targetRegion**|String|False| |探测目标region：该探测对象所在region，任务类型为2：rds、3：redis时必填<br>in: query|
|**taskType**|Long|True| |task类型：1=url/ip、2=RDS、3=redis|
|**timeout**|Long|False| |探测超时时间（单位：秒）：默认值:5，取值范围 [1,300]|
### KeyValue
|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**key**|String|False| |key|
|**value**|String|False| |value|
### Probe
|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**privateIp**|String|True| |探测源所在云主机内网ip|
|**publicIp**|String|False| |探测源所在云主机公网ip|
|**region**|String|True| |探测源所在region|
|**uuid**|String|True| |探测源所在云主机的uuid|

## 返回参数
|名称|类型|描述|
|---|---|---|
|**requestId**|String|请求的标识id|
|**result**|Result| |

### Result
|名称|类型|描述|
|---|---|---|
|**suc**|Boolean|是否创建成功|
|**taskId**|String|创建成功的规则id列表|

## 返回码
|返回码|描述|
|---|---|
|**200**|创建可用性监控任务|
