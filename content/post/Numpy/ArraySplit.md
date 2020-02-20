---
title: 4.切片与索引
summary: 数组元素的提取
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

数组切片得到的是**“视图”**，对其的改变会**同步**至原来的数组！
获得“独立”的新数组应该先`b=a.copy()`

## 关于提取列元素

```python
a=np.array([[1,2,3],
            [4,5,6],
            [7,8,9]])

b=a[:,1]
>>> [2,5,8]

c=a[:,1:2]
>>> [[2]
     [5]
     [8]]
```



获取非零元素的下标使用`nonzero()`方法