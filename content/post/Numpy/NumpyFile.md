---
title: 8.读取及写入数据文件
summary: 从CSV、DAT文件中读取数据或向其写入
date: "2020-02-28T00:00:00Z"
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

## 读取及写入CSV文件

### 一维和二维

`np.loadtxt(fname, dtype=float, delimiter=None)`
`np.savetxt(fname, arrA, fmt='%.18e', delimiter=' ')`

### 高维

`arrA=np.fromfile(file, dtype=None, sep='')`
`arrA.tofile(file, sep='', format='%d')`