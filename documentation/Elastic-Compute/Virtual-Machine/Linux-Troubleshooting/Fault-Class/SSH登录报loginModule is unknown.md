# SSH登录报login: Module is unknown




注意：本文相关 Linux 配置及说明已在 CentOS 6.5 64 位操作系统中进行过测试。其它类型及版本操作系统配置可能有所差异，具体情况请参阅相应操作系统官方文档。



**问题描述：**

使用vnc或SSH远程连接并登录 Linux云主机时，无法成功登录，而且 secure 日志中出现类似以下报错信息：

*login: Module is unknown.*

*login: PAM unable to dlopen(/lib/security/pam_limits.so): /lib/security/pam_limits.so: cannot open shared object file: No such file or directory.*



**问题原因：**

每个启用 PAM 的应用程序，在 /etc/pam.d 目录中都有对应的同名配置文件。例如，login 命令的配置文件是 /etc/pam.d/login，可以在相应配置文件中配置具体的策略，如下所示：

文件	功能说明

/etc/pam.d/login	控制台（vnc）对应配置文件

/etc/pam.d/sshd	登录对应配置文件

/etc/pam.d/system-auth	系统全局配置文件

远程连接登录时，某些启用了 PAM 的应用程序加载模块失败，导致配置了相应策略的登录方式交互失败。这里主要查看 /etc/pam.d/sshd 和 /etc/pam.d/system-auth 路径，vnc登录的 /etc/pam.d/login 配置文件出错时，需要重启服务器进入单用户模式查看。


**解决方法：**

无法通过服务器管理员账号密码登录时

1.通过vnc登录 Linux 云主机。

2.执行命令 cat filename 查看 PAM 配置文件，如 cat /etc/pam.d/login 和 cat /etc/pam.d/system-auth。

3.检查配置文件是否有类似如下配置信息，如，本文检查到 /etc/pam.d/system-auth 配置文件中有如下配置信息。

*session    required     pam_limits.so*

