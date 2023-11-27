# 第一章 Shell概述
- <img width="657" alt="image" src="https://github.com/13378144607/Linux-Shell/assets/131531888/f356759c-bfa9-488a-8ed2-f60e48c7742d">

1. Linux 提供的 Shell 解析器有
   ```shell
    [atguigu@hadoop101 ~]$ cat /etc/shells
    /bin/sh
    /bin/bash
    /usr/bin/sh
    /usr/bin/bash
    /bin/tcsh
    /bin/csh
   ```
2. bash和sh的关系
   ```shell
     [atguigu@hadoop101 bin]$ ll | grep bash
     -rwxr-xr-x. 1 root root 941880 5 月 11 2016 bash
     lrwxrwxrwx. 1 root root 4 5 月 27 2017 sh -> bash
   ```
3. Centos 默认的解析器是 bash
   ```shell
    [atguigu@hadoop101 bin]$ echo $SHELL
    /bin/bash
   ```
# 第二章 Shell脚本入门
1. 脚本格式
   脚本以#!/bin/bash 开头（指定解析器）
2. 第一个 Shell 脚本：helloworld.sh
   2.1 需求：创建一个 Shell 脚本，输出 helloworld
   2.2 案例实操
     ```shell
     [atguigu@hadoop101 shells]$ touch helloworld.sh [atguigu@hadoop101 shells]$ vim helloworld.sh
     在 helloworld.sh 中输入如下内容
     #!/bin/bash
     echo "helloworld"
     ```
    2.3 脚本的常用执行方式
     第一种：采用 bash 或 sh+脚本的相对路径或绝对路径（不用赋予脚本+x 权限）


   
