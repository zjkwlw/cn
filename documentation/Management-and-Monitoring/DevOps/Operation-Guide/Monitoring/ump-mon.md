---
title: 'ump监控'
---
# ump监控
## 基本概念

#### 方法性能监控

对被监控方法或代码段的执行时间以毫秒为单位进行统计分析，产生出统计参数指标供参考和作为报警依据。

#### TP指标

**TP****指标: TP50：**指在一个时间段内（如5分钟），统计该方法每次调用所消耗的时间，并将这些时间按从小到大的顺序进行排序，取第50%的那个值作为TP50 值；配置此监控指标对应的报警阀值后，需要保证在这个时间段内该方法所有调用的消耗时间至少有50%的值要小于此阀值，否则系统将会报警。

**TP90****，TP99，TP999**与TP50值计算方式一致，它们分别代表着对方法的不同性能要求，TP50相对较低，TP90则比较高，TP99，TP999则对方法性能要求很高。

#### 成功率

成功率=（**调用总次数**-调用失败次数）/**调用总次数**

#### 自定义监控

当应用系统根据判断达到某种情况需要报警时直接进行报警，主要应用于以下场景：

（1）用于应用程序发生异常被捕获时发送报警通知，detail可以设置为指定的错误信息描述。

（2）根据业务逻辑判断，需要报警时发出报警通知，例如某个接口调用失败，或某个业务执行失败等等。

#### JVM监控

用于实时监控java应用虚拟机资源使用情况。监控的服务有：监控JVM的CPU，堆和非堆内存使用情况，Full GC，Young GC情况，JVM开启线程数，提供实时的数据展示。

## 如何接入云翼监控

### 1. 支持的ump监控

我们支持ump用户将以下三种监控接入云翼监控中，成功接入后即可在ark“智能监控—趋势图”查看采集的数据，以及在“智能监控-监控配置”中配置报警。

| **ump****监控** | **支持的接入方式** | **查看趋势图**                                               | **报警通知**                                                 |
| --------------- | ------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| 方法性能监控    | 自动接入           | 直接在【趋势图】查看数据                                     | 须在【监控配置】创建报警                                     |
|                 | 手动接入           | 1） 须先在【监控配置】添加采集配置，将key值与应用关联  <br /> 2） 在【趋势图】查图 | 须在【监控配置】创建报警                                     |
| JVM监控         | 自动接入           | 直接在【趋势图】查看数据                                     | 须在【监控配置】创建报警                                     |
| 自定义监控      | 自动接入           | 无趋势图                                     | a. 通常须在【监控配置】创建报警   <br />b. 对于调用方法时直接传入报警接收人的ump自定义监控，无需另配报警，可直接发送报警通知 |

### 2.接入方式说明

* 自动接入：在下文的接入步骤（1）中，用户调用ump函数时须传入appName参数，将应用与key值关联，此后无需在云翼监控中增加采集配置即可查看趋势图。

* 手动接入：仅适用于方法性能监控。调用ump函数时如未传入appName参数，用户可在云翼监控中增加采集配置，关联节点与ump监控。


### 3. <a name="1">接入步骤</a>

#### 1. java项目调用ump相关函数

```java
<dependency> 

    <groupId>com.jd.ump</groupId> 

    <artifactId>hawkeye-profiler</artifactId> 

    <version>0.0.1-SNAPSHOT</version> 

</dependency> 
```

#### 2. 安装agent
**下载**

a) 公有云环境agent下载

* <http://storage-jd-local-jcloud-admin.proxy.jd.com/ump-rsyslog/ump-rsyslog-jcloud_online_ec8838a_20180426145208.bin>

b) Devops环境(iaas虚拟机)agent下载

* 华北 <http://hawkeye.oss.cn-north-1.jcloudcs.com/ump-rsyslog-jcloud_devops_online_0533327_20180917125948.bin>

* 广州 <http://hawkeye-gz.oss.cn-south-1.jcloudcs.com/ump-rsyslog-jcloud_devops_online_0533327_20180917125948.bin>

* 宿迁 <http://hawkeye-sq.oss.cn-east-1.jcloudcs.com/ump-rsyslog-jcloud_devops_online_0533327_20180917125948.bin>

* 上海 <http://hawkeye-sh.oss.cn-east-2.jcloudcs.com/ump-rsyslog-jcloud_devops_online_0533327_20180917125948.bin>


**安装**:   ```sh ./ump-rsyslog-jcloud_devops_online_0533327_20180917125948.bin```

### 3.查看趋势图/添加报警
 自动接入：直接直接在【趋势图】看图

 手动接入：须先在【监控配置】添加采集配置，将key值与应用关联,然后即可在【趋势图】查图 

## 问题排查
ump监控无数据时如何排查问题？

- 建KEY规则：只能由字母、数字、下划线、中划线、点组成，且长度不能大于128位。（全局唯一）

- 监控数据检查
  - 检查监控日志文件是否已经生成

    路径：/export/home/tomcat/UMP-Monitor/logs/*.log；

    日志文件不存在请检查UMP代码接入是否正确

  - 日志文档中的KEY是否有您要查看的KEY

    grep -il "key"  /export/home/tomcat/UMP-Monitor/logs/*.log

    确认方法已经被调用，并已生成监控数据日志

- 环境检查

  - ​	时区时间是否正确（指的的日志上生成的时间是否正确，非机器时间）

    时间：与北京时间误差小于1分钟（日志内的时间）

    时区：CST时区

  - ​	<a href="#1">日志采集客户端rsyslog</a>：

    权限检查：rsyslog启动帐号是否有 /export/home/tomcat/UMP-Monitor/logs/*.log的读权限

    进程检查：检查进程进否已经启动→  ps -ef | grep ump-rsyslog

    日志检查：

    启动：`/export/servers/ump-rsyslog-jcloud/bin/control start`

    停止：`/export/servers/ump-rsyslog-jcloud/bin/control stop`


其他相关问题可[查看ump帮助文档](https://cf.jd.com/pages/viewpage.action?pageId=73251808) 。