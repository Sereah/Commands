# Commands
Commands learned during work.



#### Android命令

###### 查看apk包

> adb shell pm list packages -a -f |grep com.xxx.xxxx



###### 查看系统android版本

> adb shell getprop ro.build.version.release



###### adb进入QNX，视不同的项目而定

> busybox telnet 172.31.207.204





#### Carplay开发命令

###### 查看mfi usb驱动状态

> dmesg |grep usbmfi



###### 有线连接前切换对应USB口为主机模式，插上CP后，CP会将USB口切换为从设备模式

> echo host > /sys/devices/platform/soc/a800000.ssusb/mode



###### USB连接需要将USB网卡添加到路由，这个视不同的项目而定

> ip -6 route add default dev mfincm0 table local_network proto static scope link metric 512





#### Ubuntu使用命令

###### ubuntu下更改DNS域名

> /etc/resolv.conf
