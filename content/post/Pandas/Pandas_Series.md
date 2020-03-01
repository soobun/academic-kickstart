---
title: Pandas之Series
date: "2020-03-01T00:00:00Z"
tags: ["Pandas"]
reading_time: false  # Show estimated reading time?
share: false  # Show social sharing links?
profile: false  # Show author profile?
comments: false  # Show comments?
# Optional header image (relative to `static/img/` folder).
header:
  caption: ""
  image: ""
---

## 创建、使用Series

```
import pandas as pd
import numpy as np
s1=pd.Series(25,index=['a','b','c'])  #从标量创建，必须有index参数
s1
```




    a    25
    b    25
    c    25
    dtype: int64




```
d1={'a':1,'b':2,'c':3}
s2=pd.Series(d1)    #从字典创建，也可通过index参数指定索引次序
s2
```




    a    1
    b    2
    c    3
    dtype: int64




```
s2.index  #获取索引
```




    Index(['a', 'b', 'c'], dtype='object')




```
s2.values #获取值
```




    array([1, 2, 3])




```
s2.name='给个名字'
s2
```




    a    1
    b    2
    c    3
    Name: 给个名字, dtype: int64


