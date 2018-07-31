# 计费规则

## 计费项

<table border=0 cellpadding=0 cellspacing=0 width=840 style='border-collapse:
 collapse;table-layout:fixed;width:632pt'>
 <col class=xl65 width=110 style='mso-width-source:userset;mso-width-alt:3520;
 width:83pt'>
 <col class=xl65 width=106 style='mso-width-source:userset;mso-width-alt:3392;
 width:80pt'>
 <col class=xl65 width=216 style='mso-width-source:userset;mso-width-alt:6912;
 width:162pt'>
 <col class=xl65 width=339 style='mso-width-source:userset;mso-width-alt:10858;
 width:255pt'>
 <col class=xl65 width=69 style='width:52pt'>
 <tr height=19 style='height:14.0pt'>
  <td colspan=2 height=19 class=xl66 width=216 style='height:14.0pt;width:163pt'>计费项</td>
  <td class=xl66 width=216 style='border-left:none;width:162pt'>释义</td>
  <td class=xl66 width=339 style='border-left:none;width:255pt'><span
  style='mso-spacerun:yes'>&nbsp;</span>计费公式</td>
  <td class=xl66 width=69 style='border-left:none;width:52pt'><span
  style='mso-spacerun:yes'>&nbsp;</span>说明</td>
 </tr>
 <tr height=56 style='height:42.0pt'>
  <td rowspan=2 height=131 class=xl67 width=110 style='height:98.0pt;
  border-top:none;width:83pt'><span style='font-variant-ligatures: normal;
  font-variant-caps: normal;orphans: 2;text-align:start;widows: 2;-webkit-text-stroke-width: 0px;
  text-decoration-style: initial;text-decoration-color: initial'>存储容量</span></td>
  <td class=xl68 width=106 style='border-top:none;border-left:none;width:80pt'><span
  style='font-variant-ligatures: normal;font-variant-caps: normal;orphans: 2;
  text-align:start;widows: 2;-webkit-text-stroke-width: 0px;text-decoration-style: initial;
  text-decoration-color: initial'>实际存储空间占用量</span></td>
  <td class=xl69 width=216 style='border-top:none;border-left:none;width:162pt'>实际存储空间占用量包括：<br>
    1.标准存储类型的数据占用量<br>
    2.低冗余类型的数据占用量</td>
  <td class=xl68 width=339 style='border-top:none;border-left:none;width:255pt'><span
  style='font-variant-ligatures: normal;font-variant-caps: normal;orphans: 2;
  text-align:start;widows: 2;-webkit-text-stroke-width: 0px;text-decoration-style: initial;
  text-decoration-color: initial'>当前存储容量（GB）* 对应存储类型的每天单价</span></td>
  <td class=xl70 width=69 style='border-top:none;border-left:none;width:52pt'><span
  style='font-variant-ligatures: normal;font-variant-caps: normal;orphans: 2;
  text-align:start;widows: 2;-webkit-text-stroke-width: 0px;text-decoration-style: initial;
  text-decoration-color: initial'>具体价格请查阅价格总览</span></td>
 </tr>
 <tr height=75 style='height:56.0pt'>
  <td height=75 class=xl68 width=106 style='height:56.0pt;border-top:none;
  border-left:none;width:80pt'><span style='font-variant-ligatures: normal;
  font-variant-caps: normal;orphans: 2;text-align:start;widows: 2;-webkit-text-stroke-width: 0px;
  text-decoration-style: initial;text-decoration-color: initial'>数据取回量</span></td>
  <td class=xl71 width=216 style='border-top:none;border-left:none;width:162pt'><span
  style='font-variant-ligatures: normal;font-variant-caps: normal;orphans: 2;
  text-align:start;widows: 2;-webkit-text-stroke-width: 0px;text-decoration-style: initial;
  text-decoration-color: initial'>对于低冗余存储类型数据的访问，会按照读取文件的大小计算数据取回量，不区分内、外网。</span></td>
  <td class=xl69 width=339 style='border-top:none;border-left:none;width:255pt'>数据取回量费用
  = 数据取回量（GB） * 每 GB 单价<br>
    例：假如您需要从低冗余存储类型的Bucket中下载10个文件，每个文件10GB。那么数据取回的费用 = 10 * 10 * 每GB的数据取回单价</td>
  <td class=xl72 width=69 style='border-top:none;border-left:none;width:52pt'>目前免费</td>
 </tr>
 <tr height=56 style='height:42.0pt'>
  <td rowspan=6 height=317 class=xl67 width=110 style='height:238.0pt;
  border-top:none;width:83pt'><span style='font-variant-ligatures: normal;
  font-variant-caps: normal;orphans: 2;text-align:start;widows: 2;-webkit-text-stroke-width: 0px;
  text-decoration-style: initial;text-decoration-color: initial'>访问流量</span></td>
  <td class=xl73 width=106 style='border-top:none;border-left:none;width:80pt'>内网流入流量</td>
  <td class=xl73 width=216 style='border-top:none;border-left:none;width:162pt'>通过京东云内网从云主机等内部服务上传数据到对象存储所产生的上行流量</td>
  <td class=xl73 width=339 style='border-top:none;border-left:none;width:255pt'>-</td>
  <td class=xl74 width=69 style='border-top:none;border-left:none;width:52pt'>免费</td>
 </tr>
 <tr height=56 style='height:42.0pt'>
  <td height=56 class=xl73 width=106 style='height:42.0pt;border-top:none;
  border-left:none;width:80pt'>内网流出流量</td>
  <td class=xl73 width=216 style='border-top:none;border-left:none;width:162pt'>通过京东云内网从对象存储下载数据到云主机等内部服务所产生的下行流量</td>
  <td class=xl73 width=339 style='border-top:none;border-left:none;width:255pt'>-</td>
  <td class=xl74 width=69 style='border-top:none;border-left:none;width:52pt'>免费</td>
 </tr>
 <tr height=37 style='height:28.0pt'>
  <td height=37 class=xl73 width=106 style='height:28.0pt;border-top:none;
  border-left:none;width:80pt'>外网流入流量</td>
  <td class=xl73 width=216 style='border-top:none;border-left:none;width:162pt'>通过公网从本地端上传数据到京东云对象存储所产生的上行流量</td>
  <td class=xl73 width=339 style='border-top:none;border-left:none;width:255pt'>-</td>
  <td class=xl74 width=69 style='border-top:none;border-left:none;width:52pt'>免费</td>
 </tr>
 <tr height=56 style='height:42.0pt'>
  <td height=56 class=xl73 width=106 style='height:42.0pt;border-top:none;
  border-left:none;width:80pt'>外网流出流量</td>
  <td class=xl73 width=216 style='border-top:none;border-left:none;width:162pt'>通过公网从京东云对象存储下载数据到本地端所产生的下行流量</td>
  <td class=xl73 width=339 style='border-top:none;border-left:none;width:255pt'>每天累计外网流出流量（GB）
  * 每 GB 单价</td>
  <td class=xl74 width=69 style='border-top:none;border-left:none;width:52pt'>具体价格请查阅价格总览</td>
 </tr>
 <tr height=56 style='height:42.0pt'>
  <td height=56 class=xl73 width=106 style='height:42.0pt;border-top:none;
  border-left:none;width:80pt'>CDN回源流出流量</td>
  <td class=xl73 width=216 style='border-top:none;border-left:none;width:162pt'>通过CDN服务层下载
  OSS 的数据所产生的回源下行流量</td>
  <td class=xl73 width=339 style='border-top:none;border-left:none;width:255pt'>每天累计
  CDN 回源流出流量（GB） * 每 GB 单价跨区域复制流量</td>
  <td class=xl74 width=69 style='border-top:none;border-left:none;width:52pt'>具体价格请查阅价格总览</td>
 </tr>
 <tr height=56 style='height:42.0pt'>
  <td height=56 class=xl73 width=106 style='height:42.0pt;border-top:none;
  border-left:none;width:80pt'>跨区域复制流量</td>
  <td class=xl73 width=216 style='border-top:none;border-left:none;width:162pt'>使用跨区域复制功能将源
  Bucket 的数据同步复制到目标 Bucket 时所产生的流出流量</td>
  <td class=xl73 width=339 style='border-top:none;border-left:none;width:255pt'>每天累计跨区域复制流量（GB）
  * 每 GB 单价</td>
  <td class=xl74 width=69 style='border-top:none;border-left:none;width:52pt'>目前免费</td>
 </tr>
 <tr height=37 style='height:28.0pt'>
  <td rowspan=2 height=74 class=xl66 width=110 style='height:56.0pt;border-top:
  none;width:83pt'>请求次数</td>
  <td class=xl73 width=106 style='border-top:none;border-left:none;width:80pt'>GET请求</td>
  <td class=xl73 width=216 style='border-top:none;border-left:none;width:162pt'>对象存储OPEN
  API当中全部GET请求</td>
  <td class=xl73 width=339 style='border-top:none;border-left:none;width:255pt'>每天累计GET请求总数/10000
  * 每万次请求单价</td>
  <td class=xl74 width=69 style='border-top:none;border-left:none;width:52pt'>目前免费</td>
 </tr>
 <tr height=37 style='height:28.0pt'>
  <td height=37 class=xl73 width=106 style='height:28.0pt;border-top:none;
  border-left:none;width:80pt'>PUT请求</td>
  <td class=xl73 width=216 style='border-top:none;border-left:none;width:162pt'>对象存储OPEN
  API当中全部PUT请求</td>
  <td class=xl73 width=339 style='border-top:none;border-left:none;width:255pt'>每天累计PUT请求总数/10000
  * 每万次请求单价</td>
  <td class=xl74 width=69 style='border-top:none;border-left:none;width:52pt'>目前免费</td>
 </tr>
 <![if supportMisalignedColumns]>
 <tr height=0 style='display:none'>
  <td width=110 style='width:83pt'></td>
  <td width=106 style='width:80pt'></td>
  <td width=216 style='width:162pt'></td>
  <td width=339 style='width:255pt'></td>
  <td width=69 style='width:52pt'></td>
 </tr>
 <![endif]>
</table>

## 计费案例

**案例背景1（使用标准型存储）**

A公司是一家传媒企业，会把大量图片素材文件放在对象存储上，采用标准存储方式，大约有100GB左右图片文件，每月图片文件的外网下行流量大约为500GB，不使用CDN加速，每月大概200万次读请求或写请求。

费用组成

存储容量费用：100（GB） * 0.00427元/GB/天 * 30（天） = 12.81元

外网下行流量费用：500（GB） * 0.50元/GB = 250.00元

请求次数费用：暂时免费，若收费，则此部分费用为 200（万次） / 10000  * 单价/万次

总月消费 = 存储容量费用 + 外网下行流量费用 = 12.81元 + 250.00元 = 262.81元

**案例背景2（使用对象存储+CDN）**

B公司是一家视频网站企业，会把大量视频文件放在对象存储上，采用标准存储方式，大约有200GB左右视频文件，每月视频文件使用CDN加速，CDN公网流量大约为4TB，CDN回源流量大约为800GB（若访问CDN节点没有命中待访问的文件，则回源到对象存储去获取），每月大概500万次读请求或写请求。

费用组成

存储容量费用：200（GB） * 0.00427元/GB/天 * 30（天） = 25.62元

CDN回源流量费用：800（GB） * 0.14元/GB = 112.00元

CDN公网流量费用：4 * 1024（GB） * 0.35元/GB = 1433.60元

请求次数费用：暂时免费，若收费，则此部分费用为 500（万次） / 10000  * 单价/万次

总月消费 = 存储容量费用 + CDN回源流量费用 + CDN公网流量费用 = 25.62元 + 112.00元 + 1433.60元 = 1571.22元

**案例背景3（使用低冗余型存储）**

C公司是一家电商企业，会把大量电子发票文件放在对象存储上做数据冷备，采用低频访问型存储方式，大约有500TB左右电子发票文件，极少访问，目前阶段外网下行流量可以估算为0，请求次数也可以估算为0。

费用组成

存储容量费用：500（TB） * 1024 *  0.00233元/GB/天 * 30（天） = 35788.80元

外网下行流量费用： 0.00元

请求次数费用：暂时免费

总月消费 = 存储容量费用 + 外网下行流量费用 = 35788.80元 + 0.00元 = 35788.80元

