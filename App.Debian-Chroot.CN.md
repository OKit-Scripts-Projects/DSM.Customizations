# Debian Chroot魔改包
## 简介
去年刚开始用群晖的时候，我发现我的平台上官方没有提供可用的debian，今年我又看了以下，可以自行编译。

踩了很多坑后，我给debian 源码打了适配补丁, 现在可以在DSM6.1~6.2的平台上运行了。参考了[这条 Issue](https://github.com/SynoCommunity/spksrc/issues/1910)

这个包目前在群晖的很多平台上都运行成功了,可以放心下载。

Debian-Chroot包是依赖python的，因为python编译太慢了，而且往往群晖套件中心都能下载到，所以就没有提供python包，只提供了bromolow平台的python(在zip里)，如有需要，提Issue，我空了编译给你。

## 声明
0. 我的软件是装在`volume2`的, 所以接下来的演示代码中包含`volume2`的代码,需要你把它替换成你自己的软件盘，通常默认是`volume1`.

## 说明 !!!
***群晖网页界面里的Debian-Chroot软件可以打开界面，但是状态栏是读不到数据的，不用管它***

***网页界面启动debian-Chroot就完成使命了.你也可以把debian启动命令写在开机启动脚本里***

***尽量都用shell来操作***

SSH 到 DSM6.x, 输入以下命令

0. `/var/packages/debian-chroot/scripts/start-stop-status start # debian启动命令`
1. `chroot /volume2/\@appstore/debian-chroot/var/chroottarget /bin/bash # Chroot 的进入命令`

(`/volume2` 把 volume2 换成你自己存软件的卷,通常是volume1)

现在你就已经成功进入Debian-Chroot了.

### 开启服务附加步骤
如果你需要开机启动一些debian里的服务, 那就在群晖的网页界面添加开机计划任务，把类似以下的代码添加进开机脚本。

0. `chroot /volume2/\@appstore/debian-chroot/var/chroottarget '/etc/init.d/cron' 'start' # 这用来启动Debian里的定时任务`

类似的，你可以用这样的代码来启动你的其他服务，如ssh之类的。

### 注意
0. 有人说安装好debian以后可能需要重启群晖，如果你遇到安装好以后有运行问题，那么重启试试看。

## 下载连接
包太多我就不一一指明了，你可以通过查看群晖官方的[型号架构对应表](https://www.synology.com/zh-tw/knowledgebase/DSM/tutorial/General/What_kind_of_CPU_does_my_NAS_have)来确定你需要安装哪个包。

[百度网盘](https://pan.baidu.com/s/1Tyumk7eHX5TekH5wiegMUg)


## 运行平台
我用的是 DS3615xs

如果你需要其他平台的包，你可以看这个库里的编译教程，自己编译。

或者就提个Issue，我空了给你编译。

## Debian初始化命令
0. `apt update`
0. `apt upgrade`
0. `dpkg-reconfigure tzdata`
0. `apt install locales`
0. `dpkg-reconfigure locales`

## 使用建议
如果你觉得这个库有用，那给颗★是最好的支持，让更多人看到这个库。

Happy hacking! 

## 参考资料
0. [查一下你的群晖是什么架构](https://www.synology.com/zh-tw/knowledgebase/DSM/tutorial/General/What_kind_of_CPU_does_my_NAS_have)

