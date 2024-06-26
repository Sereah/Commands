# Commands
Commands learned during work.



#### Android命令

###### 查看apk包

> adb shell pm list packages -a -f |grep com.xxx.xxxx



###### 查看系统android版本

> adb shell getprop ro.build.version.release



###### adb进入QNX，视不同的项目而定

> busybox telnet 172.31.207.204



###### 拉取Android源码

> repo init -u https://android.googlesource.com/platform/manifest -b android-14.0.0_r33 --repo-url clone.bundle



###### 拉取AOSP Car-libs源码

> repo init -u https://android.googlesource.com/platform/manifest -b ub-automotive-master-20231102 --repo-url clone.bundle



###### 导入framework.jar编译

> 设置bootstrapClasspath
> 例如：

```yaml
gradle.projectsEvaluated {
    tasks.withType(JavaCompile).tap {
        configureEach {
            List<File> newFileList = new ArrayList<>()
            newFileList.add(rootProject.file(branch_path + '/ext/framework-bluetooth.jar'))
            newFileList.add(rootProject.file(branch_path + '/ext/framework-wifi.jar'))
            newFileList.addAll(options.bootstrapClasspath.getFiles())
            options.bootstrapClasspath = files(newFileList.toArray())
        }
    }
}
```





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
