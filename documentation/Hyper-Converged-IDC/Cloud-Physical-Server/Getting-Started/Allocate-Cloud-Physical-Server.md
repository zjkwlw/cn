## 配置云物理服务器

- 配置地域与可用区

![配置地域与可用区](https://github.com/jdcloudcom/cn/blob/edit/image/Hyper-Converged-IDC/Cloud-Physical-Server/CPS012.png)

- 配置主机规格：
参考[产品规格](../Introduction/Specifications.md)。

- 选取镜像

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;例如，现阶段支持“标准镜像”和“标准镜像+应用”两种镜像类型。

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;其中“标准镜像”支持CentOS6.6、7.1、7.2和7.5，Ubuntu14.04和16.04；“标准镜像+应用”支持CentOS6.6和CentOS7.2下的Nginx、MySQL和RabbitMQ三个应用。详细情况参见[镜像使用说明](../Operation-Guide/Image/Description-Image.md)。

![镜像选择](https://github.com/jdcloudcom/cn/blob/edit/image/Hyper-Converged-IDC/Cloud-Physical-Server/CPS014.png)

- 配置存储：

选取系统盘和数据盘的RAID模式。

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;（说明：某些机型的系统盘或数据盘RAID模式是固定的，请根据实际情况做选择，详情参见[产品规格](../Introduction/Specifications.md)。）

![配置存储](https://github.com/jdcloudcom/cn/blob/edit/image/Hyper-Converged-IDC/Cloud-Physical-Server/CPS015.png)

- 配置网络

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **内部网络** ：基础网络模式下，用户只有第一次配置网络的时候可以选择内网CIDR地址段。后续创建的云物理服务器将使用第一次配置的内网CIDR地址段。

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **防火墙** ：操作系统安装完成后，系统对外网网络只开放IN方向的22端口。操作系统安装成功后，用户可自行登录操作系统更改iptable设置。详情请参考[防火墙设置操作指南](../Operation-Guide/Network-And-Security/Steps-Network-And-Security.md)。

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **公网带宽** ：用户可以选择不购买公网IP，但是后期不可添加公网IP。若选择购买公网IP，公网IP和云物理服务器带宽绑定。公网IP由系统自动分配，用户不可以修改公网IP。创建时不展示公网IP地址。创建后在列表页和详情页展示公网IP地址。基础网络模式下，用户可选择1-200Mbps的公网带宽速率。具体操作步骤参见[调整公网带宽](../Operation-Guide/Adjust-Public-Network-Bandwidth/Description.md)章节。

- 配置服务器基本信息：
配置服务器名称、描述、操作系统密码。

![配置服务器](https://github.com/jdcloudcom/cn/blob/edit/image/Hyper-Converged-IDC/Cloud-Physical-Server/CPS018.png)

- 配置购买时长：
购买时长1-9个月、1、2、3年。

![配置购买时长](https://github.com/jdcloudcom/cn/blob/edit/image/Hyper-Converged-IDC/Cloud-Physical-Server/CPS019.png)

- 点击“立即购买”按钮，跳转到订单确认页

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;按照京东云统一的订单计费流程支付成功后，跳转回控制台列表页面。
