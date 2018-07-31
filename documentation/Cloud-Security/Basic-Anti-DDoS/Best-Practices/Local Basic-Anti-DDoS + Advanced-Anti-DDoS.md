# 本地DDoS基础防护+IP高防联动方案

DDoS基础防护是为京东云用户针对常见的DDoS攻击推出的免费服务。提供最高2G的攻击防护能力。对于超过2G攻击流量的DDoS攻击，会触发黑洞，导致业务不可用。
针对此种情况，为用户提供云端联动防护功能。本地防护系统通过实时流量监测，当攻击流量达到本地防护阈值，自动将流量牵引至IP高防，帮助用户实现应急上云。
本地DDoS基础防护加云端IP高防联动方案能够满足不同用户的需求，对用户业务实现精准高效的防护。

## 防护架构

![部署架构](https://github.com/jdcloudcom/cn/blob/edit/image/Advanced%20Anti-DDoS/Best-Practice01.png)<Br/>

### 3、商用安全方案

由于基础防护只能防御小流量的基本攻击。如果需要针对大流量的攻击防御，建议您使用京东云为您提供的IP高防服务。

关于IP高防，请参见：[IP高防](https://ip-anti-console.jdcloud.com/instancelist)
