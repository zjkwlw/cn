# 自定义监控

自定义监控包含自定义脚本和单机程序http输出两种。其中，

自定义脚本：用户可自定义脚本，并在脚本中按约定的格式定义好想要输出的数据

单机程序http输出： 如想获取程序的输出结果，可按照约定的格式规范输出结果，然后通过对本机发起http请求的方式，获取输出的数据。

## 操作指南

**（1） 自定义脚本监控**

​     自定义脚本是完全根据用户编写的监控脚本来实现具体的监控内容和方式。编写的脚本必须按照以下要求：

- 用户需要指定脚本的路径

- 脚本语言无限制，监控机器能解析执行即可。shell/python/ruby等

- 脚本内需要指定解释器，且赋予$account可读可执行权限，所以编写脚本的时候需要注意

- 监控系统暂不负责脚本分发

- 脚本执行后退出状态码必须为0


​     脚本的规范如下：

```sh
[tags:k1:v1,k2:v2]

    $ItemName:$ItemValue,type:$type[,desc:%desc]
```

 其中，$ItemValue认定为double类型, 如果是"$itemValue"，则会被认定为string类型，默认只存储最新值

 $type默认为gauge, counter, counterQps，

- gauge: 不对值做任何处理，默认方式
- counter: newValue - lastValue
- counterQps: (newValue - lastValue) / cycle


 $desc是字符串，表示的是描述这个监控项的信息，只会发送给报警

 $classify是字符串，用来表示生成的监控项的类别，具体可填的类型信息[点击查看](https://cf.jd.com/pages/viewpage.action?pageId=96879313)  


```sh
   例如(不带tag)：

    \#!/bin/bash -

    echo "nginx_timeout:998.0,desc: 正常,classify:latency"
    echo "nginx_pv:10000,desc: ping不通数据库,classify:traffic"

  假如采集配置为exec_demo，上面的监控脚本产生的监控项为：
    Name:exec_demo.nginx_timeout
    Value:998.0
    
    Name:exec_demo.nginx_pv
    Value:10000.0  
```

```sh
 例如（带tag）

   \#!/bin/bash -

    echo "tags:idc:majuqiao,version:1.0"
    echo "nginx_timeout:998.0,classify:latency"
    echo "nginx_pv:10000,classify:traffic"
    echo "tags:idc:majuqiao,version:2.0"
    echo "nginx_err:78"

  比如采集配置为exec_demo，上面的监控脚本产生的监控项为：
    Name:exec_demo.nginx_timeout
    Tags:idc:majuqiao,version:1.0
    Value:998.0
       
    Name:exec_demo.nginx_pv
    Tags:idc:majuqiao,version:1.0
    Value:10000.0  
    
    Name:exec_demo.nginx_err
    Tags:idc:majuqiao,version:2.0
    Value:78  
```

生成的监控指标格式：$name.$outputMetric

**（2）单机http输出监控脚本**

单机http输出监控的目的是对本机发起http请求，检查返回的输出结果。用户指定当前机器的http端口+http监控获取路径，其中输出的格式符合指定的监控输出格式，则监控项会被自动采集.

```sh
具体的规则是：

[tags:k1:v1,k2:v2]

     $ItemName:$ItemValue[,type:$type]
```

 ​     其中$type默认为gauge, counter, counterQps

 ​     其中$ItemValue认定为double类型, 如果是"$itemValue"，则会被认定为string类型，默认只存储最新值

 ​   生成的监控指标格式：$name.$outputMetric

**示例**

如: 我们有一个报警发送模块hawkeye-sender，它实现了一个http接口/stat，暴露报警发送成功数、失败数、内部积压队列长度的指标，监听在4322端口。
curl 127.0.0.1:4322/stat
输出内容:

```
mail_cnt:12
mail_queue_size:1
sms_cnt:12
sms_queue_size:2
```

监控配置如下：

```json
{
	"method": "http",
	"para": {
		"port": "4322",
		"target": "/stat"
	},
	"cycle": 10
}
```

