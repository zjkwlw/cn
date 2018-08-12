# 自定义监控
## 自定义监控概述
自定义监控是提供给用户自由定义监控项及报警规则的一项功能。通过此功能，用户可以针对自己关心的业务指标进行监控，将采集到监控数据上报至云监控，由云监控来进行数据的处理，并根据结果进行报警。
## 应用场景
- 实时关注重点业务  通过自定义监控将某些重点业务监控数据进行上报，日常巡检就能随时查看对应视图趋势，同时可设置报警规则，一旦业务发生异常，则会立马收到短信邮件通知。
- 精准分析业务数据  自定义监控弥补了云资源监控的不足，您可将自身收集的一些业务监控该数据进行上报，通过云监控平台可视化图表的数据展示，帮助您更精准地进行统计和分析。

##  产品优势
- 简单易用  无需配置，数据上报后自动展示；报警规则设置与基础云资源无差异，延续您的使用习惯。
- 免费使用  上报、存储、计算均无需花费，帮您管理监控数据。

## 使用限制
1. 每个用户在每个地域下最多可上报20个命名空间；
2. 每个指标最多支持5个维度；
3. 只能推送过去30天之内的数据。

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


## 查看监控数据
### 查看命名空间
进入京东云控制台-云监控-自定义监控，进入自定义监控主页面，可查看到您已上报的命名空间、监控对象及指标情况。如下图所示：

![](https://raw.githubusercontent.com/jdcloudcom/cn/edit/image/Cloud-Monitor/1.%E5%91%BD%E5%90%8D%E7%A9%BA%E9%97%B4.png)

### 查看监控资源
点击命名空间的名称，可查看上报到属于该名称空间的资源情况，如下图所示：

![image](https://raw.githubusercontent.com/jdcloudcom/cn/edit/image/Cloud-Monitor/2.%E7%9B%91%E6%8E%A7%E5%AF%B9%E8%B1%A1%E5%88%97%E8%A1%A8.png)

### 查看监控图表
选中要查看的监控对象，点击操作列的“监控表”，进入监控图表详情页，可查看该监控对象的监控趋势图，如下图所示：

![image](https://raw.githubusercontent.com/jdcloudcom/cn/edit/image/Cloud-Monitor/3.%E7%9B%91%E6%8E%A7%E5%9B%BE.png)

### 删除监控数据
进入京东云控制台-云监控-自定义监控，进入自定义监控主页面。点击命名空间的名称，进入监控资源列表页面，选中要删除的监控对象，点击操作列的“删除”按钮，即可删除。

注：若删除命名空间下的全部监控对象之后，命名空间也级联删除了。
### 设置报警规则
进入京东云控制台后，在左侧菜单栏中选择-云监控-自定义监控，进入自定义监控主页面。点击命名空间的名称，进入监控资源列表页面，选中要设置规则的监控对象，点击操作列的“报警规则”，进入报警规则设置页面，如下图所示：

![image](https://raw.githubusercontent.com/jdcloudcom/cn/edit/image/Cloud-Monitor/4.%E6%8A%A5%E8%AD%A6%E8%A7%84%E5%88%99%E9%A1%B5%E9%9D%A2.png)

点击“新增报警规则”，进入报警规则页面，按照流程引导设置即可，如下图所示：

![image](https://raw.githubusercontent.com/jdcloudcom/cn/edit/image/Cloud-Monitor/5.%E8%AE%BE%E7%BD%AE%E6%8A%A5%E8%AD%A6%E8%A7%84%E5%88%99.png)

### 查看报警信息
登录京东云账号后，进入控制台页面，在左侧菜单栏中选择“管理-云监控-报警管理-历史报警信息”，进入报警信息页面，切换至“自定义监控”标签页，即可查看到自定义监控产生的报警信息。如下图所示：

![image](https://raw.githubusercontent.com/jdcloudcom/cn/edit/image/Cloud-Monitor/6.%E5%8E%86%E5%8F%B2%E6%8A%A5%E8%AD%A6%E4%BF%A1%E6%81%AF.png)
