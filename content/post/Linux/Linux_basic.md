---
title: Linux基础
summary: Linux常用的命令
date: "2020-04-17T00:00:00Z"
tags: ["Linux"]
reading_time: false  # Show estimated reading time?
share: false  # Show social sharing links?
profile: false  # Show author profile?
comments: false  # Show comments?
# Optional header image (relative to `static/img/` folder).
header:
  caption: ""
  image: ""
---

## 关机与重启

`shutdown` 关机

	`-h` 延迟（`now` 立刻；`1` 1分钟）
	`-r` 重启

`halt` 立刻关机

`reboot` 立刻重启

`sync` 保存所有设置，准备关机

## 用户管理
添加用户 `useradd` *`username`*

	`-d` 指定家目录
	`-g` 指定用户组

修改密码 `passwd` *`username`*

删除用户 `userdel` *`username`*

	`-r` 同时删除用户目录
查询用户信息 `id` *`username`*

修改用户 `usermod`

	`-g` 指定用户组
	`-d` 指定用户目录
### 用户相关配置文件的位置
用户信息 `/etc/passwd`

	每行内容为 username:x:uid:gid::home_dict:shell_dict
密码 `/etc/shadow`
组配置 `/etc/group`

## 用户组管理
`groupadd`

`groupdel`

## 运行级别
	配置文件 /etc/inittab
	0 关机
	1 单用户（找回丢失密码）
	2 多用户无网络
	3 多用户有网络
	4 未定义
	5 图形界面
	6 重启

## 文件目录类命令
`ls` 显示当前文件夹文件

	-h 选择合适单位显示文件夹

`mkdir` 创建文件夹

	`-P` 递归地创建文件夹

`\cp` 复制（强制覆盖）

`cat` 浏览文件

	`-n` 显示行号
	`|more` 分页显示

`less` 分屏显示文件（适用于大文件）

`head` 显示文件前10行内容

	`-n num` 显示前num行

`tail` 显示文件最后10行内容

	`-f` 实时监控文件更新

`ln -s source filename` 软链接（快捷方式）

`history` 查看已经执行过的历史命令

	`!178` 执行第178号历史指令

## 搜索查找类命令
`find` 查找文件

	find 搜索范围 -name 文件名
	             -user 用户名
                 -size +20M (大于20M)
					   20M  (等于20M)

`grep` 查找文件中的字符串

## 压缩类命令
`zip dest_file source_file` 压缩文件

	-r 压缩目录

`unzip` 解压文件

	-d 指定解压目录

`tar` 压缩解压

	-zcvf 压缩
	-zxvf 解压

## 权限管理
`chown username filename` 修改文件所有者

`chgrp` 修改文件所在组

`ls -l`显示目录文件详细信息

	-rw-r--r-- 1 root root 4096 Apr.15th 12:00 test.txt
	第1位：- 普通文件；d 目录；l 软链接；c 字符设备；b 块文件
	第2-4位：文件所有者权限
	第5-7位：文件所在组权限
	第8-10位：其他组权限

	文件：硬链接数量
	目录：子目录个数
	
必须有目录w权限才能删除文件

有目录x权限可进入该目录

## 任务调度
`crontab` 任务调度

	-e 编辑
	-l 查看
	-r 删除
	45 22 * * * 每天22：45执行
	0 17 * * 1	每周1的17：00执行
	0 5 1,15 * * 每月1号和15号的5：00执行
	40 4 * * 1-5 每周1到5的4：40执行
	*/10 4 * * * 每天4点每隔10分钟执行

## 磁盘情况查询
`df -h` 查询磁盘整体情况

`du -h` 查询某个目录磁盘占用情况

	--max-depth=n 仅深入至n级子目录
	-c 增加汇总
	-a 同时统计文件

`ls -l | grep "^-" | wc -l` 统计当前目录下有多少文件

`ls -lR | grep "^-" | wc -l` 统计当前目录以及子目录下有多少文件

`ls -l | grep "^d" | wc -l` 统计当前目录下有多少目录

## 进程管理
`ps -aux`

`ps -ef` 找父进程

`kill -9` 强制终止