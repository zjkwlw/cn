## 使用Kibana
### 定义索引模式
进入ES控制台，在实例列表页单击kibana，跳转到kibana web页面，单击左侧导航栏的Management ，选择Index Patterns，在该页面中可以定义新的索引模式。</br>

例如：为上一步骤中的样本数据集Shakespeare定义索引“shakes*”，然后点击“Create”。通过同样的方式可以再定义另一个索引“ba*”，单击“Add New “为上一步骤中的样本数据集logstash定义索引，勾选“Use event times to create index names [DEPRECATED]”，“Index pattern interval”下拉框中选择“Daily”，并且从下拉框“Time Filter field name ”选中“@timestamp”，然后点击”Create”，完成索引的定义。
### 检索数据
单击kibana页面左侧导航栏的“Discover”，选择对应的索引查看搜索结果。也可以通过输入特定的搜索条件在搜索框中进行检索，在搜索框中可以使用运算符>,<=，逻辑符AND OR NOT（都是大写）来进行组合检索。</br>

例如：选中“ba*”作为检索条件，在搜索框中输入“account_number:<100 AND balance:>47500”，此搜索条件将返回account_number在【0，99】之间并且balance的值大于47500的结果。</br>

![查询1](https://github.com/jdcloudcom/cn/blob/Elasticsearch/image/Internet-Middleware/JCS%20for%20Elasticsearch/kibana_1.png)
