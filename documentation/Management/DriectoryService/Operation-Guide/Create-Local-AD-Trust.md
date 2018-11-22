### 本地目录信任关系操作

1.打开服务器管理器，然后在 **Tools** 菜单上，选择 **Active Directory Domains and Trusts**。

![img](https://cf.jd.com/download/attachments/114747395/image2018-7-25%2011%3A28%3A59.png?version=1&modificationDate=1532489342000&api=v2)

2.打开域的上下文 (右键单击) 菜单，选择 **Properties**。
![img](https://cf.jd.com/download/attachments/114747395/image2018-7-25%2011%3A29%3A48.png?version=1&modificationDate=1532489389000&api=v2)

3.选择 **Trusts** 选项卡，然后选择 **New trust**。键入 AWS Managed Microsoft AD 的名称，然后选择 **Next** (下一步)。
![img](https://cf.jd.com/download/attachments/114747395/image2018-7-25%2011%3A30%3A34.png?version=1&modificationDate=1532489434000&api=v2)

4.选择 **Forest trust**。选择 **Next**。
![img](https://cf.jd.com/download/attachments/114747395/image2018-7-25%2011%3A31%3A11.png?version=1&modificationDate=1532489471000&api=v2)

5.选择 **Two-way**。选择 **Next**。
![img](https://cf.jd.com/download/attachments/114747395/image2018-7-25%2011%3A31%3A54.png?version=1&modificationDate=1532489515000&api=v2)

6.选择 **This domain only**。选择 **Next**。
![img](https://cf.jd.com/download/attachments/114747395/image2018-7-25%2011%3A31%3A28.png?version=1&modificationDate=1532489489000&api=v2)

7.选择 **Forest-wide authentication**。选择 **Next**。
![img](https://cf.jd.com/download/attachments/114747395/image2018-7-25%2011%3A32%3A29.png?version=1&modificationDate=1532489550000&api=v2)

8.键入 **Trust password**。请务必记住此密码，因为在为 AWS Managed Microsoft AD 设置信任时会需要它。
![img](https://cf.jd.com/download/attachments/114747395/image2018-7-25%2011%3A33%3A2.png?version=1&modificationDate=1532489582000&api=v2)

9.在下一个对话框中，确认设置，然后选择 **Next**。确认已成功创建信任，再次选择 **Next**。
![img](https://cf.jd.com/download/attachments/114747395/image2018-7-25%2011%3A33%3A25.png?version=1&modificationDate=1532489606000&api=v2)![img](https://cf.jd.com/download/attachments/114747395/image2018-7-25%2011%3A33%3A49.png?version=1&modificationDate=1532489629000&api=v2)

10.选择 **No, do not confirm the outgoing trust**。选择 **Next**。
![img](https://cf.jd.com/download/attachments/114747395/image2018-7-25%2011%3A34%3A14.png?version=1&modificationDate=1532489654000&api=v2)

11.选择 **No, do not confirm the incoming trust**。选择 **Next**。
![img](https://cf.jd.com/download/attachments/114747395/image2018-7-25%2011%3A34%3A35.png?version=1&modificationDate=1532489676000&api=v2)