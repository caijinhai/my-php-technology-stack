## 系统定时任务

### crontab
```linux
crontab -e
* * * * * 命令（分 时 日 月 周）
```

### at
```linux
# at 2:00 tomorrow
at > /home/do_job
at > Ctrl + D
```

## vi/vim 编辑器

### 模式类型
- 一般模式：删除、复制和粘贴
- 编辑模式
- 命令行模式

### 模式切换
- 切换编辑模式：i、I、o、O、a、A、r、R
- 切换到命令模式：：、/、？

### 编辑器配置
- setnu
- setnonu

## shell 基础

### 脚本执行方式
1、赋予权限，直接执行：
```linux
chmod +x test.sh
./test.sh
```
2、调用解释器使得脚本执行：
- bash
- ash
- bsh
- csh
- ksh

3、使用 `source` 命令：
```linux
source test.sh
```

### 脚本编写
开头用#！指定脚本解释器，如：#!/bin/sh

## Linux常用命令

### 系统安全
* sudo
* su
* chmod
* setfacl

### 进程管理
* w
* top
* ps
* kill
* pkill
* pstree
* killall

### 用户管理
* id
* usermod
* useradd
* groupadd
* userdel

### 文件系统
* mount
* umount
* fsck
* df
* du

### 系统关机和重启
* shutdown
* reboot

### 网络应用
- curl
- telnet
- mail
- elinks

### 网络测试
- ping
- netstat
- host

### 网络配置
-  hostname
-  ifconfig

### 常用工具
- ssh
- screen
- clear
- who
- date

### 软件包管理
- yum
- rpm
- apt-get

### 文件查找和比较
- locate
- find

### 文件内容查看
- head
- tail
- less
- more

### 文件处理
- touch
- unlink
- rename
- ln
- cat

### 目录操作
- cd
- mv
- rm
- pwd
- tree
- cp
- ls

### 文件权限属性
- setfacl
- chmod
- chown
- chgrp

### 压缩/解压
- bzip2/bunzip2
- gzip/gunzip
- zip/unzip
- tar

### 文件传输
- ftp
- scp
