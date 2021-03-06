# **刷新预热**

**1、控制台—位置说明**

登录CDN控制台，选择左侧菜单栏的【刷新缓存】                                              

 ![image.png](https://img1.jcloudcs.com/cms/b4021e8c-827e-4331-9617-301ea758423020180117163325.png)

**2、查询任务状态**

通过任务状态，可清楚实时查询每一个刷新或者预热的任务成功率和失败率，对于失败的任务可重试，重试后建立新的任务查看结果和状态

**![image.png](https://img1.jcloudcs.com/cms/3c752f53-54cd-4919-a95d-33f70b30c5dc20180205101014.png)**

- 任务ID，根据Unix时间戳建立，可通过任务ID实时查询任务状态和结果

- 重试机制，任务失败时可重新下发任务，重新下发的任务因时间变化会建立一个新的任务ID进行追踪

  

**3、URL刷新**

* 每个URL应以<http://>或者<https://>开头，URL刷新如果是网站URL，则刷新的是网站首页，如果全站刷新，请在目录刷新下进行，以/结尾
* 多个URL使用回车分割
* 单次最多支持刷新100个URL，每天最多可刷新（含预热）2000个URL
* 刷新任务生效时间约为5分钟。

 

**4、目录刷新**

* 每个路径应以<http://>或者<https://>开头，以/结尾
* 多个路径使用回车分割
* 单次最多支持刷新5个目录，每天最多可刷新50个目录
* 刷新任务生效时间约为5分钟

 

**5、URL预热**

* 每个URL应以<http://>或者<https://>开头
* 多个URL使用回车分割
* 单次最多支持刷新100个URL，每天最多可刷新（含预热）2000个URL
* 刷新任务生效时间约为5分钟。
