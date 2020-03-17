---
title: Zip 与 Enumerate
summary: “打包”函数
date: "2020-03-17T00:00:00Z"
tags: ["Teaching","Python"]
reading_time: false  # Show estimated reading time?
share: false  # Show social sharing links?
profile: false  # Show author profile?
comments: false  # Show comments?
# Optional header image (relative to `static/img/` folder).
header:
  caption: ""
  image: ""
---

## 用zip打包
返回一个将多个可迭代对象组合成一个元组序列的迭代器。每个元组都包含所有可迭代对象中该位置的元素。
例如，`list(zip(['a', 'b', 'c'], [1, 2, 3]))` 将输出 `[('a', 1), ('b', 2), ('c', 3)]`.
### 用星号拆分
```python
some_list = [('a', 1), ('b', 2), ('c', 3)]
letters, nums = zip(*some_list)
```

## Enumerate
enumerate 是一个会返回元组迭代器的内置函数，这些元组包含列表的索引和值。
### 自己写一个迭代器（不用`return`,用`yield`）
```python
下面是一个叫做 my_range 的生成器函数，它会生成一个从 0 到 (x - 1) 的数字流。

def my_range(x):
    i = 0
    while i < x:
        yield i
        i += 1
```



