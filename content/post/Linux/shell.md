---
title: Shell
summary: Shell的基本语法
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

# Shell变量


变量直接定义

**只读变量** `readonly`

	例如：readonly my_name=xxx

调用时变量名前加 `$` 符号，建议用大括号包裹变量名

	例如：${my_name}

**删除变量** `unset`

---

# 字符串

**单引号和双引号**

* 单引号内只能是普通字符串，不能内含单引号，不能调用变量
* 双引号内可以用转义符，可以调用变量

**字符串拼接**

字符串紧贴即可

**字符串的长度**

	str='abc'
	echo ${#str}

**获取子串**

***索引从0开始***

`${str:start:length}`

	例如：str='abcdefghijk'
	     echo ${str:1:3}
	输出 bcd

***

# 数组

**定义数组**

数组名=(值0 值1 ... 值n)

**数组长度**

`${#arr[*]}`

---

# 传递参数

执行脚本时传递的参数

* `$0` 为脚本文件名
* 后续参数分别为 `$1` `$2` ...

|参数|说明|
|----|-------|
|`$#`|参数个数|
|`$*`|显示所有参数|
|`$$`|显示当前进程ID号|

---

# 基本运算

**算术运算**


***运算符左右必须有空格***

采用 `expr num1 op num2` 形式


**关系运算**

* `-eq` 等于
* `-ne` 不等于
* `-gt` 大于
* `-ge` 大于等于
* `-lt` 小于
* `-le` 小于等于

**布尔运算**

* `!`  非
* `-o` 或
* `-a` 与

**字符串运算**

* `-z` 字符串长度是否为0
* `-n` 字符串长度是否不为0

**文件运算**

示例

```sh
file="/var/www/runoob/test.sh"
if [ -r $file ]
then
   echo "文件可读"
else
   echo "文件不可读"
fi
if [ -w $file ]
then
   echo "文件可写"
else
   echo "文件不可写"
fi
```

# 其他

`printf` 函数类似C语言，没有括号和逗号

	例如 printf %d %s 12 "abc"

[参考网址](https://www.runoob.com/linux/linux-shell-func.html "参考网址")