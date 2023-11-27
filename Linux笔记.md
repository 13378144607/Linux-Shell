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
   ![Uploading image.png…]()























