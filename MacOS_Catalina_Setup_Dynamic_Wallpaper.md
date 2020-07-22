# Catalina 相关设置
## 1. 关闭SIP系统完整性保护

1. 关机，然后重新启动你的Mac电脑，在开机时一直按住Command+R迸入Recovery模式。
2. 进入Recovery模式后打开终端，如图：
![image](https://github.com/10B-B11/image_foc_doc/blob/master/recovery-utilities-terminal.jpg)

3.在终端上输入下面命令, 然后回车。
```
csrutil disable
```

![image](https://github.com/10B-B11/image_foc_doc/blob/master/csrutil-disable.jpg)

4.点击左上角苹果图标，再点击重新启动
5.打开终端 Terminal， 输入下面命令
```
csrutil status
```

![image](https://github.com/10B-B11/image_foc_doc/blob/master/Screen%20Shot%202020-07-21%20at%2023.35.30.png)
如果返回
```
System Integrity Protection status: disabled.
```
则表明关闭成功。

5. 如果要开启SIP, 以同样的方法进入recovery模式，使用终端运行`csrutil enable`,然后重启计算机

## 2. 设置动态壁纸

1. 去[Dynamic Wallpaper Club](https://dynamicwallpaper.club/gallery)下载想要的壁纸
1. 打开Disk Utility
2. 选择正确的硬盘
3. 点击右上角的info
![image](https://github.com/10B-B11/image_foc_doc/blob/master/disk_info.png)
4. 复制BSD device node 的值 比如图中的disk1s1
![image](https://github.com/10B-B11/image_foc_doc/blob/master/device_node.png)
5. 打开终端 分别输入一下命令 (其中的disk1s1替换成上图的BSD device node的值)
```
sudo mount -t apfs -wu /dev/disk1s1 /Volumes
```
```
sudo mount -wu
```
```
killall Finder
```
6. 打开Finder (访达)
7. 点击菜单栏中GO, 选择 Go to Folder
![image](https://github.com/10B-B11/image_foc_doc/blob/master/Go_in_Finder.png)

8. 在弹出的对话框里输入 `/System/Library/Desktop Pictures/`
![image](https://github.com/10B-B11/image_foc_doc/blob/master/Go_to_Library.png)

9. 把下载好的动态壁纸拖到该文件下

10. 会弹出对话框，选择授权并输入密码

11. 打开系统设置->桌面与屏幕保护程序->桌面, 在 Apple 分类下能看见刚刚设置的 动态壁纸，选择 “动态” 选项即可。



