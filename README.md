![输入图片说明](https://images.gitee.com/uploads/images/2020/0329/060357_d50dc364_899222.jpeg "QQ截图20200329060210.jpg")
![输入图片说明](https://images.gitee.com/uploads/images/2020/0329/060408_475d69a4_899222.jpeg "QQ截图20200329060118.jpg")
 支持一下 :smile: 

```
更新日志:【2020年3月31日】
最新源码编译，优化dns
```

【2020年3月29日】小米路由器R3P 83M固件超多插件集成版

简述结尾: 有openwrt官方刷机方法

首页:
https://gitee.com/chenxqiyu/openwrt_r3p

固件仓库路径:
```
openwrt_r3p/targets/ramips/mt7621
```
固件下载路径:
```
http://chenxqiyu.gitee.io/openwrt_r3p/targets/ramips/mt7621/openwrt-ramips-mt7621-xiaomi_mir3p-squashfs-factory.bin
```
[点击下载](http://chenxqiyu.gitee.io/openwrt_r3p/targets/ramips/mt7621/openwrt-ramips-mt7621-xiaomi_mir3p-squashfs-factory.bin)（注:适用于小米官方固件首次刷入openwrt使用）
```
http://chenxqiyu.gitee.io/openwrt_r3p/targets/ramips/mt7621/openwrt-ramips-mt7621-xiaomi_mir3p-squashfs-sysupgrade.bin
```
[点击下载](http://chenxqiyu.gitee.io/openwrt_r3p/targets/ramips/mt7621/openwrt-ramips-mt7621-xiaomi_mir3p-squashfs-sysupgrade.bin)（注:适用于已是openwrt固件来更新固件）

不刷固件可添加一下仓库源地址安装插件:
```
src/gz openwrt_core http://chenxqiyu.gitee.io/openwrt_r3p/targets/ramips/mt7621/packages
src/gz openwrt_base http://chenxqiyu.gitee.io/openwrt_r3p/packages/mipsel_24kc/base
src/gz openwrt_lienol http://chenxqiyu.gitee.io/openwrt_r3p/packages/mipsel_24kc/lienol
src/gz openwrt_luci http://chenxqiyu.gitee.io/openwrt_r3p/packages/mipsel_24kc/luci
src/gz openwrt_packages http://chenxqiyu.gitee.io/openwrt_r3p/packages/mipsel_24kc/packages
src/gz openwrt_routing http://chenxqiyu.gitee.io/openwrt_r3p/packages/mipsel_24kc/routing
```
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

【刷入Openwrt】
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

【恢复到小米固件】

1、从小米下载开发固件，并将其重命名为miwifi.bin放到U盘(FAT/FAT32)根目录。

2、使用SSH（192.168.1.1）登录路由器并运行以下命令：

  fw_setenv flag_try_sys1_failed 0

  fw_setenv flag_try_sys2_failed 1

  fw_setenv flag_boot_success 0

3、关闭路由器

4、将U盘插到路由器

5、按住重置按钮并打开电源，直到黄灯亮起。等待5分钟安装固件。

6、登录到192.168.31.1的路由器。
