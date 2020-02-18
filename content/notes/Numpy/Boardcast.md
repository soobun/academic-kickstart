---
title: 7.广播
summary: 用于不同大小数组的二进制通用函数（加、减、乘等）的一组规则
date: "2020-02-18T00:00:00Z"
tags: ["Numpy"]
reading_time: false  # Show estimated reading time?
share: false  # Show social sharing links?
profile: false  # Show author profile?
comments: false  # Show comments?
# Optional header image (relative to `static/img/` folder).
header:
  caption: ""
  image: ""
---

## 广播规则

* 如果两个数组的维度数不相同，那么小维度数组的形状将会在最左边补1。

* 如果两个数组的形状在任何一个维度上都不匹配，那么数组的形状会沿着维度为1 的维度扩展以匹配另外一个数组的形状。

* 如果两个数组的形状在任何一个维度上都不匹配并且没有任何一个维度等于1，那么会引发异常。


