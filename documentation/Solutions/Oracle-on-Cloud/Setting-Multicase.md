# 设置组播

可以通过N2N软件来进行组播的实现


### 集群IP划分
#### pub
10.10.10.101 oracle-rac1

10.10.10.102 oracle-rac2

#### vip
10.10.10.103 oracle-rac1-vip

10.10.10.104 oracle-rac2-vip 

#### priv
192.168.100.101 oracle-rac1-priv 

192.168.100.102 oracle-rac2-priv 

#### scan-ip
10.10.10.105 scan-ip

### 1. 安装N2N
在所有计划安装Oracle RAC的节点上执行
```
svn co https://svn.ntop.org/svn/ntop/trunk/n2n
cd n2n/n2n_v2
make
make install
```

### 2. 启动supernode服务
在其中一个节点上启动supernode服务
```
/opt/n2n/sbin/supernode -l 65530
# 写入开机自启动
echo "/opt/n2n/sbin/supernode -l 65530" >> /etc/rc.local
```

### 3. 设置节点的多IP
以两个节点为例，同样需要写入到开始自启动中
```
# 节点1
/opt/n2n/sbin/edge -d edge0 -a 10.10.10.101 -s 255.255.255.0 -c dtstack -k dtstack -l 10.0.0.32:65530 -E -r
/opt/n2n/sbin/edge -d edge1 -a 192.168.100.101 -s 255.255.255.0 -c dtstack -k dtstack -l 10.0.0.32:65530 -E -r

# 节点2
/opt/n2n/sbin/edge -d edge0 -a 10.10.10.102 -s 255.255.255.0 -c dtstack -k dtstack -l 10.0.0.32:65530 -E -r
/opt/n2n/sbin/edge -d edge1 -a 192.168.100.102 -s 255.255.255.0 -c dtstack -k dtstack -l 10.0.0.32:65530 -E -r
```
