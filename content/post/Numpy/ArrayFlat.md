---
title: 3.数组的展开操作
summary: 数组的迭代操作
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

## flat

对数组中每个元素都进行处理，可以使用flat属性，该属性是一个数组元素迭代器

```python
a=np.array([[1,2,3],
            [4,5,6],
            [7,8,9]])
for element in a.flat:
    print(element,end=' ')
>>>1 2 3 4 5 6 7 8 9
```

## flatten()

返回一份数组拷贝，按行或列展开

```python
a=np.array([1,2,3,4],
           [5,6,7,8])
print(a.flatten(order='C'))
>>> [1,2,3,4,5,6,7,8]
print(a.flatten(order='F'))
>>> [1,5,2,6,3,7,4,8]
```

## ravel()

与`flatten()`类似，不过对其修改会影响源数组