# 手动创建备份

每个 MongoDB 实例最多可手动创建3个备份，备份文件长期保存在京东云对象存储，目前不收取任何费用。

## 注意事项

- 如当前已有3个手动备份，再次手动创建备份时会自动删除最早的一个手动备份（创建过程有弹窗提示）。
- 如当前有进行中的备份任务，则此时不能再次发起创建备份任务。

## 操作步骤

1. 登录 [MongoDB 控制台](https://mongodb-console.jdcloud.com/mongodb)。
1. 在实例列表页面，选择目标实例，点击实例名称，进入实例详情页面。
1. 在实例详情页面，依次点击备份与恢复 > 备份数据，进入备份数据页面。

   ![](https://github.com/jdcloudcom/cn/blob/master/image/mongodb/mongo-019.png)

1. 在备份数据页面，点击"创建备份"，打开创建备份确认弹窗。
1. 点击“确定”，确认执行创建备份。
1. 您可以在备份列表中查看备份状态。

## 相关参考

- [下载备份](https://github.com/jdcloudcom/cn/blob/master/documentation/Cloud-Database-and-Cache/MongoDB/Operation-Guide/Backup/DownloadBckup.md)
- [数据恢复](https://github.com/jdcloudcom/cn/blob/master/documentation/Cloud-Database-and-Cache/MongoDB/Operation-Guide/Backup/RestoreInstance.md)
- [根据备份创建实例](https://github.com/jdcloudcom/cn/blob/master/documentation/Cloud-Database-and-Cache/MongoDB/Operation-Guide/Backup/CreateInstance2.md)
- [根据时间点创建实例](https://github.com/jdcloudcom/cn/blob/master/documentation/Cloud-Database-and-Cache/MongoDB/Operation-Guide/Backup/CreateInstance3.md)