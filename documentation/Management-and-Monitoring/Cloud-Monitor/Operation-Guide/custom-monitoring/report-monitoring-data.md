## 上报监控数据
自定义监控功能为您提供上报监控数据的接口，方便您将自己采集的时序数据上报到云监控。目前支持OpenAPI的方式进行上报，可上报原始数据和已聚合的统计数据。

### 上报接口描述

1. 接口名称：putMetricData

2. 上报域名：

地域 | 域名
---|---
华北-北京 |custommetric-put-cn-north-1.monitor.jdcloudcs.com
华南-广州 |custommetric-put-cn-south-1.monitor.jdcloudcs.com
华东-宿迁 |custommetric-put-cn-east-1.monitor.jdcloudcs.com
华东-上海 |custommetric-put-cn-east-2.monitor.jdcloudcs.com
3. 支持批量上报方式。单次请求最多包含 50 个数据点；数据大小不超过 256k。


### 请求参数

名称 | 必选 | 类型 | 说明
---|---|---|---
namespace|是|String|命名空间名称。长度不超过255字节，只允许英文、数字、中文、下划线_、点。
metric|是|String|监控指标，长度不超过255字节。
dimensions|是|Map|维度,维度至少一个，最多五个 ，按照dimensionName：dimensionValue;dimensionName：dimensionValue 的格式， 只允许英文、数字、中文、下划线_、点。
timestamp|是|Long|监控数据的时间戳，不能写入过去30天的时间。
type|是|int|上报数值的类型，1为原始值，2为聚合数据。当上报聚合数据时，建议为60s的周期时进行上报、否则无法正常查询。
values|是|Map|指标值集合，key为数据类型，value为数据值，当type=1时，key只能为”value”，上报的是原始值，当type=2时，K的值可以为"avg","sum","last","max","min","count"，只支持以上类型，否则会报错，value最大值为9223372036854775807，count只支持>=0的数

### 返回参数

名称|	类型|	描述  
---|---|---
success|bool|	全部成功则返回true，否则false。     
metricDataList|ErrorMetricData[ ]|上报失败的数据        
error|error|错误信息  
 
### ErrorMetricData[ ]

名称|类型|描述   
---|---|---
data|	metricData[ ]	|写入失败的原始数据 ，该数据为用户上报的数据数据格式
errDetail|	string  |写入失败的原因   

### error

名称|类型|描述   
---|---|---
code|int|错误码。当有多个数据点写入失败时，该code为最后一个error的code。
message|string|错误信息
status|string|字符串错误码
detail|string|详细信息 

### 错误码 

返回码|描述   
---|---
400	|参数无效
403	|权限不足
429	|配额不足
500	|服务器内部错误

### 示例代码

请求示例
```
[

        {

            "namespace":"test",

            "metric":"vm.mem.usage1",

            "tags":{

                "host":"1.2.3.23",

                "datacenter":"cn-north-1 "

            },

             "timestamp":15305424971,

             "type":1,

             "values":{

             "value":"12342213"        

            }

        },

        {

            "namespace":"test1",

            "metric":"vm.cpu.usage",

            "dimensions":{

                "host":"1.2.3.19",

                "tag":"bj "

            },

             "timestamp":1530542497,

             "type":2,

             "values":{

             "avg":"80",

             "max":"32424244120"

            }

        }

]
```

### 返回代码

返回示例


```
success：

{

    "requestId": "1111",

    "result": {

        "success": true,

        "metricDataList": []

    }

}

fail：

{

    "requestId": "1111",

    "result": {

        "success": false,

        "metricDataList": [

            {

                "data": {

                    "namespace": "test",

                    "metric": "vm.mem.usage1",

                    "dimensions": {

                        "host": "1.2.3.23",

                        "tag": "cn-north-1"

                    },

                    "timestamp": 15305424971,

                    "type": 1,

                    "values": {

                        "value": "12342213"

                    }

                },

                "errDetail": "Time value only allowed Secondtimestamps,length is 10"

            }

        ]

    },

    "error": {

        "code": 400,

        "message": "INVALID_ARGUMENT",

        "status": "INVALID_ARGUMENT",

        "details": null

    }

}
```
