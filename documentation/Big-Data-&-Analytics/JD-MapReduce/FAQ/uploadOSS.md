### 如何将数据备份至OSS？

#### 准备工作
1.	用户开通Access Key。
2.	用户在创建JMR集群时打开对象存储开关。
3.	用户在JMR集群所在的区域已创建对象存储。

#### HDFS文件上传至对象存储
1.	远程登陆至JMR集群Master节点
2.	终端用户切换至hadoop
3.	执行命令{hadoop_home}/bin/hadoop fs -cp hdfs:///{hdfs_directory}/{hdfs-file} s3a://{oss-bucket-name}/{oss-file}
参数说明：
1)	{hadoop_home}：hadoop服务根目录，参考表 1
2)	{hdfs_directory}：hdfs文件目录路径
3)	{hdfs-file}：hdfs文件名
4)	{oss-bucket-name}：对象存储空间名称
5)	{oss-file}：对象存储文件名
对象存储文件下载至HDFS
1.	远程登陆至JMR集群Master节点
2.	终端用户切换至hadoop
3.	执行命令{hadoop_home}/bin/hadoop fs -cp s3a://{oss-bucket-name}/{oss-file} hdfs:///{hdfs_directory}/{hdfs-file}
参数说明：
1)	{hadoop_home}：hadoop服务根目录，参考表 1
2)	{oss-bucket-name}：对象存储空间名称
3)	{oss-file}：对象存储文件名
4)	{hdfs_directory}：hdfs文件目录路径
5)	{hdfs-file}：hdfs文件名

