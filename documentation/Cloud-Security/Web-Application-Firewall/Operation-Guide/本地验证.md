## **本地验证**

  在把业务流量切到WAF上之前，建议您先通过本地验证确保一切配置正常，WAF转发正常。本地验证需要在本地模拟接入WAF，然后访问被防护网站，验证WAF正常转发。

  通过修改本地hosts文件模拟接入WAF，将从本地访问被防护站点的请求导向WAF。

下面以Windows操作系统为例，详细介绍本地验证的步骤：

1、用记事本或notepad++等文本编辑器打开hosts文件，hosts文件一般位于C:\Windows\System32\drivers\etc\hosts路径。

具体方法：

点击开始按钮，点击运行，在弹出的对话框中输入C:\Windows\System32\drivers\etc\hosts。点击确认后选择用记事本打开

![img](file:///c:\users\zhangjingfeng\documents\jddongdong\jimenterprise\zzjf\temp\jdonline20180929111220.png) 

![img](file:///c:\users\zhangjingfeng\documents\jddongdong\jimenterprise\zzjf\temp\jdonline20180929111306.png) 

2、在最后一行添加如下内容：WAF的IP 被防护的域名。 

 ![img](file:///c:\users\zhangjingfeng\documents\jddongdong\jimenterprise\zzjf\temp\jdonline20180929112014.png) 

 3、保存hosts文件，本地ping一下被防护的域名。 

点击开始运行cmd，输入Ping+刚才写入的域名。

 4、查看结果，若显示为刚才绑定的IP地址（WAF IP地址），则验证成功。

![img](file:///c:\users\zhangjingfeng\documents\jddongdong\jimenterprise\zzjf\temp\jdonline20180929113601.png) 

若显示依然是原来的IP地址（源站IP地址），请刷新一下本地DNS缓存（cmd下输入ipconfig/flushdns命令）。

![img](file:///c:\users\zhangjingfeng\documents\jddongdong\jimenterprise\zzjf\temp\jdonline20180929113705.png) 

5、验证转发正常，确认host绑定已经生效（域名已经本地解析为WAF IP）后，打开浏览器，输入该域名进行访问。

WAF的配置正确，网站能够正常打开。