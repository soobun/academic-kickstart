---
title: 5.合并与分割
summary: 多个数组的合并与单个数组的分割
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

## 合并

```python
a=np.array([1,2,3])
b=np.array([[4,5,6],
            [7,8,9]])
c=np.vstack([a,b])	# 纵向扩展
>>>[[1,2,3],
    [4,5,6],
    [7,8,9]]

c=np.array[[1,2],
           [3,4]]
d=np.array[[5,6],
           [7,8]]
e=np.hstack([c,d])	# 横向扩展
>>>[[1,2,5,6],
    [3,4,7,8]]
```

## 分割

### np.split()

将一维数组按参数列表的下标分割成多个一维数组

```python
split(ary, indices_or_sections, axis=0)
```

### np.vsplit()

将二维数组横着切

### np.hsplit()

将二维数组竖着切