# Debian Chroot魔改包
## 简介
去年刚开始用群晖的时候，我发现我的平台上官方没有提供可用的debian，今年我又看了以下，可以自行编译。

踩了很多坑后，我给debian 源码打了适配补丁, 现在可以在DSM6.1~6.2的平台上运行了。参考了[这条 Issue](https://github.com/SynoCommunity/spksrc/issues/1910)

这个包目前在群晖的很多平台上都运行成功了,可以放心下载。

Debian-Chroot包是依赖python的，因为python编译太慢了，而且往往群晖套件中心都能下载到，所以就没有提供python包，如有需要，提Issue。

## 声明
0. 我的软件是装在`volume2`的, 所以接下来的演示代码中包含`volume2`的代码,需要你把它替换成你自己的软件盘，通常默认是`volume1`.

## 说明 !!!
***群晖网页界面里的Debian-Chroot软件可以打开界面，但是状态栏是读不到数据的，可以不用管它***

***用网页界面来启动debian-Chroot就可以了, 或者你也可以把debian启动命令写在开机启动脚本里***

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
0. [Tenhow.debian-chroot.dsm6.[1/2].bromolow](https://www.dropbox.com/s/r4udr737knvv3jo/tenhow.debian-chroot.dsm6.%5B1%3A2%5D.bromolow.zip?dl=0) [as DS3615xs] [Required by myself] √
0. [Tenhow.debian-chroot.dsm6.[1/2].apollolake](https://www.dropbox.com/s/aef5a6a70tparbc/tenhow.debian-chroot.dsm6.%5B1%3A2%5D.apollolake.zip?dl=0) [as DS918+] [Required by lordvalium] √
0. [Tenhow.debian-chroot.dsm6.[1/2].cedarview](https://www.dropbox.com/s/85kzm6pgm90imnr/tenhow.debian-chroot.dsm6.%5B1%3A2%5D.cedarview.zip?dl=0) [as DS1213+] [Required by Tao87-04] √
0. [Tenhow.debian-chroot.dsm6.[1/2].armadaxp](https://www.dropbox.com/s/04ivz8nfztg2fe9/tenhow.debian-chroot.dsm6.%5B1%3A2%5D.armadaxp.zip?dl=0) [as RS815] [Required by DzikNsk] [No Feedback Yet]
0. [Tenhow.debian-chroot.dsm6.[1/2].88f628x](https://www.dropbox.com/s/w4psq4m4dgpdy4m/tenhow.debian-chroot.dsm6.%5B1%3A2%5D.88f628x.zip?dl=0) [as DS212] [Required by balabalaman] √
0. [Tenhow.debian-chroot.dsm6.[1/2].armada375](https://www.dropbox.com/s/6oc6ioc2c7abqti/tenhow.debian-chroot.dsm6.%5B1%3A2%5D.rtd1296.zip?dl=0) [as DS215j] [Required by paul-xor] √
0. [Tenhow.debian-chroot.dsm6.[1/2].monaco](https://www.dropbox.com/s/3a6ocgfvdshzixr/tenhow.debian-chroot.dsm6.%5B1%3A2%5D.monaco.zip?dl=0) [as DS216play] [Required by d4n1elchen] √
0. [Tenhow.debian-chroot.dsm6.[1/2].armada38x](https://www.dropbox.com/s/71p8e49dwbuv3zu/tenhow.debian-chroot.dsm6.%5B1%3A2%5D.armada38x.zip?dl=0) [as DS216j] [Required by d4n1elchen] √
0. [Tenhow.debian-chroot.dsm6.[1/2].rtd1296](https://www.dropbox.com/s/6oc6ioc2c7abqti/tenhow.debian-chroot.dsm6.%5B1%3A2%5D.rtd1296.zip?dl=0) [as DS418] [Required by gypittmann] [!Not Tested Yet!] 
0. [Tenhow.debian-chroot.dsm6.[1/2].avaton](https://www.dropbox.com/s/qroxml7bi7xy2oq/tenhow.debian-chroot.dsm6.%5B1%3A2%5D.avoton.zip?dl=0) [as DS1817+] [Required by droidboxma] √


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

