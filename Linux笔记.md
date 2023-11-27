# 第一章 Linux入门
## 1.1概述
![image](https://github.com/13378144607/Linux-Shell/assets/131531888/0b9044f9-20d8-4a65-a2c5-b46f20b2fc5c)
## 1.2Linux和Windows的区别
![image](https://github.com/13378144607/Linux-Shell/assets/131531888/c00493ce-9a2b-4e07-b11f-a6b31101938d)
## 1.3Centos下载地址
![image](https://github.com/13378144607/Linux-Shell/assets/131531888/96a37b8e-c01a-4cdd-b073-1939a98933ca)
# 第二章 VM与Linux安装
## 2.1VMWare 安装
## 2.2CentOS安装
# 第三章 Linux文件与目录结构
## 3.1 Linux 文件
Linux 系统中一切皆文件。
## 3.2 Linux 目录结构
![image](https://github.com/13378144607/Linux-Shell/assets/131531888/e9206291-eccc-4ae5-b777-42344136baac)
**目录结构简介**
![image](https://github.com/13378144607/Linux-Shell/assets/131531888/04febc02-3401-40c0-97bc-df22aee955eb)
![image](https://github.com/13378144607/Linux-Shell/assets/131531888/d6aeb594-d249-4726-8e72-3942f0407766)
![image](https://github.com/13378144607/Linux-Shell/assets/131531888/8652fdde-1968-4cc0-9135-b49a3274b74c)
![image](https://github.com/13378144607/Linux-Shell/assets/131531888/adf77ddb-dc07-43f2-865a-d54120454280)
![image](https://github.com/13378144607/Linux-Shell/assets/131531888/2449f525-10fc-4707-ac73-ec25adfbe977)
# 第四章 VI/VIM 编辑器（重要）
## 4.1是什么
  VI 是 Unix操作系统和类 Unix操作系统中最通用的文本编辑器。
  VIM 编辑器是从 VI 发展出来的一个性能更强大的文本编辑器。可以主动的以字体颜
色辨别语法的正确性，方便程序设计。VIM 与 VI 编辑器完全兼容。
## 4.2测试数据准备
- 拷贝/etc/profile 数据到/root 目录下
```shell
[root@hadoop100 桌面]# cp /etc/profile /root
[root@hadoop100 桌面]# cd /root/
```
## 4.3一般模式
  以 vi 打开一个档案就直接进入一般模式了（这是默认的模式）。在这个模式中， 你可 以使用『上下左右』按键来移动光标，你可以使用『删除字符』或『删除整行』来处理档
案内容， 也可以使用『复制、粘贴』来处理你的文件数据。
| 语法           | 功能描述                        |
| -------------- | ------------------------------- |
| yy             | 复制光标当前一行                |
| y 数字  y      | 复制一段（从第几行到第几行）    |
| p              | 箭头移动到目的行粘贴            |
| u              | 撤销上一步                      |
| dd             | 删除光标当前行                  |
| d 数字 d       | 删除光标（含）后多少行          |
| x              | 剪切一个字母，相当于  del       |
| X              | 剪切一个字母，相当于  Backspace |
| yw             | 复制一个词                      |
| dw             | 删除一个词                      |
| shift+6（  ^） | 移动到行头                      |
| shift+4 （$）  | 移动到行尾                      |
| 1+shift+g      | 移动到页头，数字                |
| shift+g        | 移动到页尾                      |
| 数字+shift+g   | 移动到目标行                    |
![image](https://github.com/13378144607/Linux-Shell/assets/131531888/f2be74ab-19e6-49f5-ba74-188130a26e85)
## 4.4编辑模式
  **在一般模式中可以进行删除、复制、粘贴等的动作，但是却无法编辑文件内容的！**要
等到你按下『i, I, o, O, a, A』等任何一个字母之后才会进入编辑模式。
  注意了！通常在Linux中，按下这些按键时，在画面的左下方会出现『INSERT或
REPLACE』的字样，此时才可以进行编辑。而如果要回到一般模式时， 则必须要按下
『Esc』这个按键即可退出编辑模式。
1. 进入编辑模式
   | 按键 | 功能               |
| ---- | ------------------ |
| i    | 当前光标前         |
| a    | 当前光标后         |
| o    | 当前光标行的下一行 |
| I    | 光标所在行最前     |
| A    | 光标所在行最后     |
| O    | 当前光标行的上一行 |
2. 退出编辑模式
   按『Esc』键 退出编辑模式，之后所在的模式为一般模式。
## 4.5 指令模式
  在一般模式当中，输入『 : / ?』3个中的任何一个按钮，就可以将光标移动到最底下那
一行。
  在这个模式当中， 可以提供你『搜寻资料』的动作，而读取、存盘、大量取代字符、
离开 vi 、显示行号等动作是在此模式中达成的！
1. 基本语法
    | 命令          | 功能                             |
    | ------------- | -------------------------------- |
    | :w            | 保存                             |
    | :q            | 退出                             |
    | :!            | 强制执行                         |
    | /要查找的词   | n 查找下一个，N 往上查找         |
    | :noh          | 取消高亮显示                     |
    | :set nu       | 显示行号                         |
    | :set nonu     | 关闭行号                         |
    | :%s/old/new/g | 替换内容 /g 替换匹配到的所有内容 |
2. 案例实操
   - 强制保存退出：`:wq!`
## 4.6 模式间转换
![image](https://github.com/13378144607/Linux-Shell/assets/131531888/114a082c-cd48-45cc-94b4-59c807c58713)
# 第五章 网络配置（重点）
## 5.1 查看网路ip和网关
1. 查看虚拟网络编辑器![image](https://github.com/13378144607/Linux-Shell/assets/131531888/e9fa50be-cac8-47cf-98ec-023a983203f2)
2. 修改虚拟网卡ip![image](https://github.com/13378144607/Linux-Shell/assets/131531888/d94d771f-8822-4732-8a83-370a9031bbaf)
3. 查看网关![image](https://github.com/13378144607/Linux-Shell/assets/131531888/3396019b-025b-4672-a82d-a830629cb44c)
4. 查看 windows 环境的中 VMnet8 网络配置![image](https://github.com/13378144607/Linux-Shell/assets/131531888/a22b9f50-aa89-463e-ac6c-29ff80093688)
## 5.2 配置网络ip地址
### 5.2.1 ifconfig配置网络接口
ifconfig :network interfaces configuring 网络接口配置
1. 基本语法
   ifconfig     （功能描述：显示所有网络接口的配置信息）
2. 案例实操
 - 查看当前网络ip
   ```shell
   ifconfig
   ```
### 5.2.2ping测试主机之间的网络连通性
1. 基本语法
   - ping 目的主机    （功能描述：测试当前服务器是否可以连接目的主机）
2. 案例实操
   - 测试当前是否能连接百度
     ```shell
     ping www.baidu.com
     ```
### 5.2.3修改ip地址
1. 查看ip配置文件
   ```shell
   vim /etc/sysconfi/network-script/ifcfg/ens33
   ```
   ![image](https://github.com/13378144607/Linux-Shell/assets/131531888/3cec0299-8830-4068-88ff-4a4d419bbecc)
   以下需要进行修改：
   > BOOTPROTO="static" 
   以下需要进行添加：
   > #IP 地址                                                                      
     IPADDR=192.168.1.100                                             
     #网关                                                                         
     GATEWAY=192.168.1.2                                            
     #域名解析器                                                                    
     DNS1=192.168.1.2
   
   ![image](https://github.com/13378144607/Linux-Shell/assets/131531888/fc0ea4ab-dd8b-437b-93b3-de18beb002be)
2. 执行 service network restart 重启网络![image](https://github.com/13378144607/Linux-Shell/assets/131531888/e95ee529-e354-4db9-bef9-45c3c9a908c7)
### 5.2.4 修改 IP 地址后可能会遇到的问题
1. 物理机能 ping 通虚拟机，但是虚拟机 ping 不通物理机,一般都是因为物理机的防火墙问题,把防火墙关闭就行
2. 虚拟机能 Ping 通物理机,但是虚拟机 Ping 不通外网,一般都是因为 DNS 的设置有问题
3. 虚拟机 Ping www.baidu.com 显示域名未知等信息,一般查看 GATEWAY 和 DNS 设置是否正确
4. 如果以上全部设置完还是不行，需要关闭 NetworkManager 服务
 - systemctl stop NetworkManager  关闭
 - systemctl disable NetworkManager 禁用
5. 如果检查发现 systemctl status network 有问题 需要检查 ifcfg-ens33
## 5.3配置主机名
### 5.3.1 修改主机名称
1. 基本语法
   hostname      显示主机名字
   hostnamectl set-hostname   修改后的主机名字
2. 实例实操
   - 查看当前服务器主机名称
     ```shell
     [root@hadoop100 桌面]# hostname
     ```
   - 如果感觉此主机名不合适，我们可以进行修改。通过编辑/etc/hostname文件
   ```shell
   [root@hadoop100 桌面]# vi /etc/hostname
   ```
  修改完成后重启生效。

### 5.3.2修改hosts映射文件
1. 修改 linux 的主机映射文件（hosts文件）后续在 hadoop 阶段，虚拟机会比较多，配置时通常会采用主机名的方式配置， 比较简单方便。 不用刻意记 ip 地址。
   - 打开/etc/hosts
     ```shell
     [root@hadoop100 桌面]# vim /etc/hosts
     ```
     添加以下内容
     ```shell
      192.168.2.100 hadoop100
      192.168.2.101 hadoop101
      192.168.2.102 hadoop102
      192.168.2.103 hadoop103
      192.168.2.104 hadoop104
      192.168.2.105 hadoop105
     ``` 
   - 重启设备，重启后，查看主机名，已经修改成功
2. 修改 windows 的主机映射文件（hosts文件）
   - 进入 C:\Windows\System32\drivers\etc 路径
   - 打开 hosts文件并添加如下内容
     ```shell
      192.168.2.100 hadoop100
      192.168.2.101 hadoop101
      192.168.2.102 hadoop102
      192.168.2.103 hadoop103
      192.168.2.104 hadoop104
      192.168.2.105 hadoop105
     ```
## 5.4 远程登录
  通常在工作过程中，公司中使用的真实服务器或者是云服务器，都不允许除运维人员 之外的员工直接接触，因此就需要通过远程登录的方式来操作。所以，远程登录工具就是 必不可缺的， 目前， 比较主流的有 Xshell, SSH Secure Shell, SecureCRT,FinalShell 等，同学
们可以根据自己的习惯自行选择.
# 第六章 系统管理
## 6.1 Linux中的进程和服务
  计算机中，一个正在执行的程序或命令，被叫做“进程 ”（process）。
  启动之后一只存在、常驻内存的进程，一般被称作“服务 ”（service）。
## 6.2 service 服务管理（CentOS 6 版本- 了解）
1. 基本语法
  service  服务名 start | stop |· restart | status
2. 经验技巧
  查看服务的方法：/etc/init.d/服务名 ,发现只有两个服务保留在 service
  ```shell
  [root@hadoop100 init.d]# pwd
  /etc/init.d
  [root@hadoop100 init.d]# ls -al
  
  drwxr-xr-x.  2	root	root	4096	3 月	19 15:24 .
  drwxr-xr-x. 10	root	root	4096	3 月	19 15:24 ..
  -rw-r--r--.  1	root	root	18104	1 月	3 2018 functions
  -rwxr-xr-x.  1	root	root	4334	1 月	3 2018 netconsole
  -rwxr-xr-x.  1	root	root	7293	1 月	3 2018 network
  -rw-r--r--.  1	root	root	1160	4 月	11 2018 README
  ```
3. 案例实操
   - 查看网络服务的状态
     ```shell
     [root@hadoop100 桌面]#service network status
     ```
   - 停止网络服务
     ```shell
     [root@hadoop100 桌面]#service network stop
     ```
   - 启动网络服务
     ```shell
     [root@hadoop100 桌面]#service network start
     ```
   - 重启网络服务
     ```shell
     [root@hadoop100 桌面]#service network restart
     ```
## 6.3  chkconfig 设置后台服务的自启配置（CentOS 6 版本）
1. 基本语法
   >  chkconfig                         （功能描述：查看所有服务器自启配置）
      chkconfig 服务名 off  （功能描述：关掉指定服务的自动启动）
      chkconfig 服务名 on   （功能描述：开启指定服务的自动启动）
      chkconfig 服务名 --list   （功能描述：查看服务开机启动状态）

2.实例实操
 - 开启/关闭 network(网络)服务的自动启动
   ```shell
   [root@hadoop100 桌面]#chkconfig network on
   [root@hadoop100 桌面]#chkconfig network off
   ```
  - 开启/关闭network 服务指定级别的自动启动
    ```shell
    [root@hadoop100 桌面]#chkconfig --level 指定级别 network on
    [root@hadoop100 桌面]#chkconfig --level 指定级别 network off
    ```
## 6.4 systemctl（CentOS版本重点掌握）
1. 基本语法
   `systemctl start | stop | restart | status`    服务名
2. 经验技巧
   查看服务的方法：`/usr/lib/systemd/system`
   ```shell
    [root@hadoop100 system]#	pwd	
    /usr/lib/systemd/system
    [root@hadoop100 init.d]#	ls -al	
    -rw-r--r--. 1 root root	275 4 月	27 2018 abrt-ccpp.service
    -rw-r--r--. 1 root	root	380	4 月	27	2018	abrtd.service
    -rw-r--r--. 1 root	root	361	4 月	27	2018	abrt-oops.service
    -rw-r--r--. 1 root	root	266	4 月	27	2018	abrt-pstoreoops.service
    -rw-r--r--. 1 root	root	262	4 月	27	2018	abrt-vmcore.service
    -rw-r--r--. 1 root	root	311	4 月	27	2018	abrt-xorg.service
    -rw-r--r--. 1 root	root	751	4 月	11	2018	accounts-daemon.service
    -rw-r--r--. 1 root	root	527	3 月	25	2017	alsa-restore.service
    -rw-r--r--. 1 root
    ……	root	486	3 月	25	2017	alsa-state.service
   ```
3. 案例实操
   - 查看防火墙服务的状态
     ```shell
     [root@hadoop100 桌面]# systemctl status firewalld
     ```
   - 停止防火墙服务
     ```shell
     [root@hadoop100 桌面]# systemctl stop firewalld
     ```
   - 启动防火墙服务
     ```shell
     [root@hadoop100 桌面]# systemctl start firewalld
     ```
   - 重启防火墙服务
     ```shell
     [root@hadoop100 桌面]# systemctl restart firewalld
     ```
## 6.5 systemctl设置后台服务的自启配置
1. 基本语法
   `systemctl list-unit-files`           （功能描述：查看服务开机启动状态）
   `systemctl disable service_name`      （功能描述：关掉指定服务的自动启动）
   `systemctl enable service_name `      （功能描述：开启指定服务的自动启动）
2. 案例实操
   - 开启/关闭 iptables(防火墙)服务的自动启动
     ```shell
     [root@hadoop100 桌面]# systemctl enable firewalld.service
     [root@hadoop100 桌面]# systemctl disable firewalld.service
     ```
## 6.6 系统运行级别
1. Linux 运行级别[CentOS 6]![image](https://github.com/13378144607/Linux-Shell/assets/131531888/c446a5fb-397c-41d5-b266-79b627fff945)
2. CentOS7 的运行级别简化为:
   - `multi-user.target` 等价于原运行级别 3（多用户有网，无图形界面）
   - `graphical.target`  等价于原运行级别 5（多用户有网，有图形界面）
3. 查看当前运行级别
   - `systemctl get-default`
4. 修改当前运行级别
   - `systemctl set-default TARGET.target`    （这里 TARGET 取 multi-user 或者 graphical）

## 6.7 关闭防火墙
1. 临时关闭防火墙
   - 查看防火墙状态
     ```shell
     [root@hadoop100 桌面]# systemctl status firewalld
     ```
   - 临时关闭防火墙
     ```shell
     [root@hadoop100 桌面]# systemctl stop firewalld
     ```
2. 开机启动时关闭防火墙
  - 查看防火墙开机启动状态
    ```shell
    [root@hadoop100 桌面]# systemctl enable firewalld.service
    ```
  - 设置开机时关闭防火墙
    ```shell
    [root@hadoop100 桌面]# systemctl disable firewalld.service
    ```
## 6.8 关机重启命令
在 linux领域内大多用在服务器上，很少遇到关机的操作。毕竟服务器上跑一个服务是永无止境的，除非特殊情况下，不得已才会关机。
1. 基本语法
   - `syc`                       （功能描述：将数据由内存同步到硬盘中）
   - `halt`                        （功能描述：停机，关闭系统，但不断电）
   - `poweroff`               （功能描述：关机，断电）
   - `reboot`                    （功能描述：就是重启，等同于 shutdown -r now）
   - `shutdown [选项] 时间`
   >| 选项 | 功能                |
   | ---- | ------------------- |
   | -H   | 相当于--halt ，停机 |
   | -r   | -r=reboot 重启      |

   >| 参数 | 功能                               |
   | ---- | ---------------------------------- |
   | now  | 立刻关机                           |
   | 时间 | 等待多久后关机（时间单位是分钟）。 |






