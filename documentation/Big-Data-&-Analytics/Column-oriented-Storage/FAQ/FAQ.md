# 常见问题

## 列式存储产品的内网及公网访问模式？

目前列式存储提供了内网及公网访问模式。
内网访问稳定安全，适合生产使用；公网访问适合开发测试访问，主要是满足开发测试需求。

使用HBase Shell访问
### 操作步骤

1. 准备访问用京东云云主机
访问HBase，建议在相同的VPC网络内准备一台云主机。

2. 安装jdk
rpm -ivh jdk-8u171-linux-x64.rpm

3. 安装hbase客户端
获取安装包 hbase-1.3.1-bin.tar.gz
解压缩：tar zxvf hbase-1.3.1-bin.tar.gz

4. 配置ZK地址
修改conf/hbase-site.xml文件，添加集群的ZK地址，如下：
<configuration>
     <property>
         <name>hbase.zookeeper.quorum</name>
         <value>$ZK_IP1,$ZK_IP2,$ZK_IP3</value>
     </property>
</configuration>
其中的$ZK_IP1,$ZK_IP2,$ZK_IP3请查看详情中列式存储地址。

5. 配置JAVA_HOME 
修改conf/hbase-env.sh文件中JAVA_HOME路径。
export JAVA_HOME=/usr/java/jdk1.8.0_171-amd64

6. 配置hosts
登录到集群任一节点主机，获取集群hosts信息，并添加到本地hosts。

7.访问集群
通过如下命令访问集群
bin/hbase shell

通过API访问
### 操作步骤
目前列式存储hbase集群支持三种API访问方式，分别为Native Java API、Thrift API、REST API，推荐使用Native Java API。

1. Native Java API
最常规高效的访问方式，使用方法请参考demo文件HbaseUtil.java。

2. Thrift API
Thrift API利用Thrift序列化技术，提供多种语言支持，使用方法请参考demo文件ThriftDemo.py。

以下是python通过Thrift API访问集群的步骤
安装依赖包:
tar zxvf pip-18.1.tar.gz
cd pip-18.1/
python setup.py install

unzip setuptools-40.6.2.zip
cd setuptools-40.6.2/
python setup.py install

如果测试机有公网权限使用安装thrift hbase-thrift
pip install thrift
pip install hbase-thrift

如果无外网权限，需使用离线安装。
tar zxvf thrift-0.11.0.tar.gz
cd thrift-0.11.0
python setup.py install

tar zxvf hbase-thrift-0.20.4.tar.gz
cd hbase-thrift-0.20.4
python setup.py install

执行Demo
python ThriftDemo.py

3. REST API 
REST API解除了语言限制，支持REST风格的HTTP API访问数据库，使用方法请参考demo文件ThriftDemo.py。

