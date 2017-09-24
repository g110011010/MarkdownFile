## openSUSE 下安装VirtualBox
1. 刚开始我是直接进行安装，但是程序会报错（-1908）
2. 首先执行一下命令,安装一些必须的依赖包：
> zypper in gcc gcc-c++ kernel-source kernel-syms

3. 安装virtualbox
> zypper in virtualbox
4. 将当前用户加入组virtualusr,方法为进入Yast,Security and Users>User and Group Managerment;进入管理界面后选择当前用户，然后点击Edit>Details,在Additional Groups中选中vboxusers,然后一路ok即可。
5. 此时在启动器中System> Oracle Vm VirtualBox即可正常启动虚拟机软件。

## VirtualBox中安装虚拟机
1. 在软件主界面点击new，输入虚拟机名称，选择系统名称和版本，然后点击next
2. 设置虚拟机内存大小，这个根据自己硬件情况进行设定，一般靠近建议内存大小最大值部分就好，点next
3. 创建虚拟硬盘点击Create
4. 没特别要求的话直接点击Next
5. 可以选择磁盘动态分配或者固定大小，其中动态分配是根据需要占据磁盘，更灵活。固定分配执行速度更快。选择好后 点击next。
6.  选择虚拟机要放置的位置，选择的位置一定要满足虚拟机对硬盘大小的要求，设定虚拟硬盘大小。点击Create.
7. 此时会回到程序主界面，这时不要急着装系统，建议首先选中刚创建的虚拟机，然后Setting>System>Processor.将虚拟机能使用的CPU的核心数适当调高，因为程序默认虚拟机的CPU利用核心只有1个，在现在CPU普遍多核心的情况下调高CPU核心数可以加快安装速度以及安装成功后的执行速度，设置好后点击ok
8. 点击start，然后在弹出的界面中选择要安装的系统的镜像文件（×.iso），然后就可以开始正常安装系统了。
## VirtualBox中实现主机与虚拟机之间文件夹共享
> 以下实现的是主机为Linux（openSUSE）。虚拟机为WIndows的环境实现文件夹共享

1. 设置要共享的文件夹：Setting>share folder>右侧加号：
![这里写图片描述](http://img.blog.csdn.net/20170923093634896?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvZzExMDAxMTAxMA==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)
2. 选择要共享的文件夹，点选Auto-mount和Make Permanent,确定
3. 在虚拟机运行界面：Devices>Insert Guest Additions ...(最下面)，根据提示安装运行软件，重启后在文件管理器，网络里面即可看到要共享的文件夹：
![这里写图片描述](http://img.blog.csdn.net/20170923094417336?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvZzExMDAxMTAxMA==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

## VirtualBox下设置虚拟机能够连接外网IPV6
> 由于学校内网中提供了很多IPV6资源，而我的Windows在虚拟机中安装着，虚拟机默认网络设置无法正常链接IPV6.

1. 在virtualbox界面：Setting>Network,进行配置如下，即可正常链接。
![这里写图片描述](http://img.blog.csdn.net/20170923101541810?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvZzExMDAxMTAxMA==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)