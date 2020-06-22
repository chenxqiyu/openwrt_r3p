![输入图片说明](https://images.gitee.com/uploads/images/2020/0329/060357_d50dc364_899222.jpeg "QQ截图20200329060210.jpg")
![输入图片说明](https://images.gitee.com/uploads/images/2020/0329/060408_475d69a4_899222.jpeg "QQ截图20200329060118.jpg")
 支持一下 :smile: 

```
更新日志:【2020年4月25日】
最新源码编译，修正samba网络共享，增加ddns动态dns客户端

更新日志:【2020年4月6日】
最新源码编译，增加挂载U盘和硬件自动设备

更新日志:【2020年3月31日】
最新源码编译，优化dns
```

【2020年4月25日】小米路由器R3P 83M固件超多插件集成版



 **注意：已是Openwrt的用户，第一次刷以下固件，强烈建议刷回官方系统以后，再刷以下提供的factory底包，防止内核不同导致变砖** 

 **注意：已是Openwrt的用户，第一次刷以下固件，强烈建议刷回官方系统以后，再刷以下提供的factory底包，防止内核不同导致变砖** 

 **注意：已是Openwrt的用户，第一次刷以下固件，强烈建议刷回官方系统以后，再刷以下提供的factory底包，防止内核不同导致变砖** 



固件下载路径:
----------------------------------------------------------------------------------------------------------------------------

```
openwrt-ramips-mt7621-xiaomi_mir3p-squashfs-factory.bin
https://pan.baidu.com/s/1WXzqWvOkpkaFOqqp2j_1OQ  提取码: g778
```
[点击下载](https://pan.baidu.com/s/1WXzqWvOkpkaFOqqp2j_1OQ)（ **注:openwrt-ramips-mt7621-xiaomi_mir3p-squashfs-factory.bin适用于小米官方系统首次刷入openwrt系统使用，为了保证成功刷入，所以不加入下面的插件，防止锁uboot没有安全模式导致变砖。刷机完成后，再更新下面的固件即可获得全部插件，更新方法看本文结尾。已是openwrt系统直接刷下面的固件即可。** ）

----------------------------------------------------------------------------------------------------------------------------

```
openwrt-ramips-mt7621-xiaomi_mir3p-squashfs-sysupgrade.bin
链接: https://pan.baidu.com/s/1Em1na5htEdoCL_2SSTjeYA 提取码: divx
```
[点击下载](https://pan.baidu.com/s/1Em1na5htEdoCL_2SSTjeYA)（ **注:openwrt-ramips-mt7621-xiaomi_mir3p-squashfs-sysupgrade.bin适用于已是openwrt系统来更新固件，更新才会有以下所有插件。** ）

```
1.更新固件方法,scp上传到路由器/tmp目录，win7和xp使用winscp，win10系统按住shift+右键使用powershell当前目录执行：

scp .\openwrt-ramips-mt7621-xiaomi_mir3p-squashfs-sysupgrade.bin root@192.168.1.1:/tmp

2.路由器ssh执行：

cd /tmp

sysupgrade -n openwrt-ramips-mt7621-xiaomi_mir3p-squashfs-sysupgrade.bin   (-n代表不保存配置更新，取消则保留配置，首次更新建议-n)

执行后自动重启，完成升级

开机成功后关闭负载均衡，否则会网络断流：
ssh到路由器复制下面命令，执行。

cd /etc/config;mv mwan3 mwan3.bak;touch mwan3;

重启即可
```
----------------------------------------------------------------------------------------------------------------------------



 **不刷固件可添加一下仓库源地址安装插件:** 
```
src/gz openwrt_core http://chenxqiyu.gitee.io/openwrt_r3p/targets/ramips/mt7621/packages
src/gz openwrt_base http://chenxqiyu.gitee.io/openwrt_r3p/packages/mipsel_24kc/base
src/gz openwrt_lienol http://chenxqiyu.gitee.io/openwrt_r3p/packages/mipsel_24kc/lienol
src/gz openwrt_luci http://chenxqiyu.gitee.io/openwrt_r3p/packages/mipsel_24kc/luci
src/gz openwrt_packages http://chenxqiyu.gitee.io/openwrt_r3p/packages/mipsel_24kc/packages
src/gz openwrt_routing http://chenxqiyu.gitee.io/openwrt_r3p/packages/mipsel_24kc/routing
```
----------------------------------------------------------------------------------------------------------------------------

固件初始账密:
```
root/password
```
固件截图：
![输入图片说明](https://images.gitee.com/uploads/images/2020/0329/062640_897db8fb_899222.jpeg "0.jpg")
![输入图片说明](https://images.gitee.com/uploads/images/2020/0329/060252_0bac71f6_899222.jpeg "2.jpg")
![输入图片说明](https://images.gitee.com/uploads/images/2020/0329/060338_8609d585_899222.jpeg "8.jpg")
![输入图片说明](https://images.gitee.com/uploads/images/2020/0329/060318_4b47f17b_899222.jpeg "5.jpg")
![输入图片说明](https://images.gitee.com/uploads/images/2020/0329/060304_b5b5f0c3_899222.jpeg "6.jpg")
![输入图片说明](https://images.gitee.com/uploads/images/2020/0329/060329_ef223521_899222.jpeg "7.jpg")
![输入图片说明](https://images.gitee.com/uploads/images/2020/0329/072716_574cb3dd_899222.jpeg "4.jpg")
![输入图片说明](https://images.gitee.com/uploads/images/2020/0401/005339_28a69375_899222.jpeg "QQ截图20200329093133.jpg")
![输入图片说明](https://images.gitee.com/uploads/images/2020/0401/005353_30ccdece_899222.jpeg "QQ截图20200329154613.jpg")
![输入图片说明](https://images.gitee.com/uploads/images/2020/0401/005417_b4df614f_899222.jpeg "pro.jpg")

【首次刷入Openwrt】

```
将提供的固件下载后放到U盘，然后插到路由器。

1、拥有SSH访问权限。(这个不用说了，要刷机的人都知道)

2、使用SSH（192.168.31.1）登录路由器。在SSH控制台中运行以下命令（注意：单独执行每行命令）

3、
cd /extdisks/sda1 (如果卸下并重新插入U盘，可能会有所不同)

mv openwrt-ramips-mt7621-xiaomi_mir3p-squashfs-factory.bin factory.bin (改个短的文件名，可以提前改好放到U盘）

nvram set flag_try_sys1_failed=1

nvram set flag_try_sys2_failed=0

nvram set flag_boot_success=0

nvram commit

dd if=factory.bin bs=1M count=4 | mtd write - kernel1

mtd erase rootfs0

mtd erase rootfs1

mtd erase overlay

dd if=factory.bin bs=1M skip=4 | mtd write - rootfs0

reboot
```

【恢复到小米固件】

```

1、从小米下载开发固件，并将其重命名为miwifi.bin放到U盘(FAT/FAT32)根目录。

2、使用SSH（192.168.1.1）登录路由器并运行以下命令：

  fw_setenv flag_try_sys1_failed 0

  fw_setenv flag_try_sys2_failed 1

  fw_setenv flag_boot_success 0

3、关闭路由器

4、将U盘插到路由器

5、按住重置按钮并打开电源，直到黄灯亮起。等待5分钟安装固件。

6、登录到192.168.31.1的路由器。

```
【刷过openwrt误刷包长亮黄灯恢复步骤】

```
进安全模式看看，

1. 关电，拔网线，插电，快闪桶孔，出现快速闪红灯，
2. 插上lan网线，进入192.168.1.1 ssh(没有获取到手动指定)，
3. mount_root,解锁uboot（fw。。。参考【恢复到小米固件】），
4. 刷回官方先，
5 .再重新刷openwrt。

不能进快闪红灯，就要ttl救机，或送修。

ttl救机相关教程参考链接
http://www.right.com.cn/forum/thread-3138721-1-1.html
```
