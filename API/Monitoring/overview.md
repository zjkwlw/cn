# JCLOUD MONITOR API


## 简介
monitor API


### 版本
v1


## API
|接口名称|请求方式|功能描述|
|---|---|---|
|**applyTemplate**|POST|应用报警模板到资源|
|**batchCreateAlarms**|POST|批量创建报警规则，可以为多个实例创建多个报警规则。|
|**batchDeleteAlarms**|DELETE|批量删除规则|
|**batchDescribeMetricData**|GET|查看某资源多个监控项数据，metric介绍：<a href="https://docs.jdcloud.com/cn/monitoring/metrics">Metrics</a>|
|**batchDisableAlarms**|POST|批量禁用规则|
|**batchEnableAlarms**|POST|批量启用规则|
|**createAlarm**|POST|创建报警规则，可以为某一个实例创建报警规则，也可以为多个实例同时创建报警规则。|
|**createAlarmCm**|POST|创建自定义监控规则|
|**createProbeTask**|POST|创建可用性监控任务|
|**createTemplate**|POST|创建自定义报警模板|
|**deleteAlarmsCm**|DELETE|删除自定义监控规则|
|**deleteNamespace**|DELETE|删除自定义监控命名空间|
|**deleteObj**|DELETE|删除obj|
|**deleteProbeTask**|DELETE|删除可用性监控任务|
|**deleteTemplates**|DELETE|批量删除自定义报警模板|
|**describeAlarmContacts**|GET|查询规则的报警联系人|
|**describeAlarmHistory**|GET|查询报警历史</br>检索条件组合优先级从高到低为</br>1. serviceCode</br>1.1 serviceCode + resourceId</br>1.2 serviceCode + resourceIds</br>2. serviceCodes</br>3. 用户所有规则|
|**describeAlarmHistoryAllRegion**|POST|查询报警历史</br>检索条件组合优先级从高到低为</br>1. serviceCode</br>1.1 serviceCode + resourceId</br>1.2 serviceCode + resourceIds</br>2. serviceCodes</br>3. 用户所有规则|
|**describeAlarmHistoryAllRegionCm**|GET|查询自定义监控所有region规则告警历史|
|**describeAlarmHistoryCm**|GET|查询自定义监控规则告警历史|
|**describeAlarmingRules**|GET|尚未恢复的告警查询接口|
|**describeAlarms**|GET|查询规则, 查询参数组合及优先级从高到低为：</br>1：serviceCode不为空</br>1.1：serviceCode + resourceId</br>1.2: serviceCode + resourceIds</br>2：serviceCodes不为空</br>3: 所有规则|
|**describeAlarmsByID**|GET|查询规则详情|
|**describeAlarmsByID**|GET|查询自定义监控规则|
|**describeAlarmsCm**|GET|查询自定义监控规则|
|**describeAllRegionAlarmsCm**|GET|查询所有region的自定义监控规则|
|**describeCmMetricDataByTagSpec**|GET|查询自定义监控项数据|
|**describeIsUserNew**|GET|查询是否是新用户|
|**describeMetricData**|GET|查看某资源多个监控项数据，metric介绍1：<a href="https://docs.jdcloud.com/cn/monitoring/metrics">Metrics</a>|
|**describeMetricDataAm**|GET|查看某资源的监控数据|
|**describeMetricDataCm**|POST|查询自定义监控的metric数据|
|**describeMetrics**|GET|根据产品线查询可用监控项列表,metric介绍：<a href="https://docs.jdcloud.com/cn/monitoring/metrics">Metrics</a>|
|**describeMetricsCm**|GET|查询自定义监控的metric列表|
|**describeMetricsForCreateAlarm**|GET|查询可用创建监控规则的指标列表,metric介绍：<a href="https://docs.jdcloud.com/cn/monitoring/metrics">Metrics</a>|
|**describeMetricsForCreateTemplate**|GET|根据产品线查询查询可以创建模板的metric|
|**describeNamespaces**|GET|查询自定义监控命名空间列表|
|**describeObj**|GET|查询obj|
|**describeObjsByNsUID**|GET|查询obj列表|
|**describeProbeHistory**|GET|查询可用性监控任务的指定探测源的异常探测历史|
|**describeProbeTask**|GET|查询可用性监控任务|
|**describeProbeTasks**|GET|查询可用性监控任务列表|
|**describeRuleCounting**|GET|概览页规则统计接口|
|**describeSqlserverBlockProcess**|GET|为阻塞进程数提供的特殊接口|
|**describeTemplates**|GET|查询报警模板|
|**describeTemplatesByTemplateID**|GET|根据模板ID查询报警模板|
|**describeTopNSlowSql**|GET|查看sqlserver数据库某资源一段时间内的topN慢sql数据|
|**disableAlarm**|POST|禁用报警规则。报警规则禁用后，将停止探测实例的监控项数据。|
|**discribeProbes**|GET|查询 可用性监控任务的探测源列表|
|**enableAlarm**|POST|启用报警规则，当客户的报警规则处于停止状态时，可以使用此接口启用报警规则。|
|**lastDownsample**|GET|查看某资源的最后一个点,metric介绍：<a href="https://docs.jdcloud.com/cn/monitoring/metrics">Metrics</a>|
|**probeTaskEnable**|POST|启用、禁用可用性监控任务|
|**putMetricData**|POST|该接口为自定义监控数据上报的接口，方便您将自己采集的时序数据上报到云监控。不同region域名上报不同region的数据，参考：<a href="https://docs.jdcloud.com/cn/monitoring/reporting-monitoring-data">调用说明</a>可上报原始数据和已聚合的统计数据。支持批量上报方式。单次请求最多包含 50 个数据点；数据大小不超过 256k。|
|**updateAlarm**|PATCH|修改已创建的报警规则|
|**updateAlarmCm**|PATCH|更新自定义监控规则|
|**updateProbeTask**|PATCH|修改可用性监控任务|
|**updateTemplate**|PATCH|更新自定义报警模板|
