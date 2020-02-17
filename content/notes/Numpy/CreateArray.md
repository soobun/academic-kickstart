---
title: CreateArray
summary: 在Numpy中初始化一个数组
date: "2020-02-17T00:00:00Z"
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

## array

手动输入数组

## zeros

元素全是0的数组

## ones

元素全是1的数组

## eye

生成单位矩阵

```python
eye(N, M=None, k=0, dtype=float, order='C')
```

例如

> ```python
> >>> np.eye(2, dtype=int)
>     array([[1, 0],
>            [0, 1]])
> >>> np.eye(3, k=1)
>     array([[ 0.,  1.,  0.],
>            [ 0.,  0.,  1.],
>            [ 0.,  0.,  0.]])
> ```

## arange

类似于Python的`range()` 方法

```python
np.arange(start, stop, step, dtype)
```

## full

生成各个元素相同的数组

```python
np.full(shape, fill_value, dtype=None, order='C')
```

## linspace

生成一个一维等差数列数组

```python
np.linspace(start, stop, num=50, endpoint=True, retstep=False, dtype=None)
```

## logspace

生成一个一维等比数列

```python
np.logspace(start, stop, num=50, endpoint=True, base=10.0, dtype=None)
```

base 参数意思是取对数的时候 log 的下标。



## random.random

生成0~1均匀分布的数组

```python
np.random.random(shape)
```

## random.normal

生成指定均值`loc`和方差`scale`的正态分布数组

```python
np.random.normal(loc=0.0, scale=1.0, size=None)
```

## random.randint

生成[start,end)之间随机整数数组

```python
np.random.randint(low, high=None, size=None, dtype='l')
```

