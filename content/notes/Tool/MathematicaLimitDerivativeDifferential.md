---
title: Mathematica 求极限、导数和微分
summary: Mathematica 求极限、导数和微分
date: "2020-02-20T18:15:00Z"
tags: ["Math","Tool"]
reading_time: false  # Show estimated reading time?
share: false  # Show social sharing links?
profile: false  # Show author profile?
comments: false  # Show comments?
# Optional header image (relative to `static/img/` folder).
header:
  caption: ""
  image: ""
---

## 求极限

语法`Limit[expr,x->x0]` 
参数`Assumptions` 设定参数满足条件
       `Direction`    设置变量变化方向
        `Analytic`     设置是否以解析式计算

```mathematica
Limit[a^(1/n), n -> \[Infinity]]
Limit[Sin[m*x]/Sin[n*x], x -> \[Pi], Assumptions -> {m, n} \[Element] Integers]
```

## 求导数和微分

| 命令           | 功能             | 例子                   |
| -------------- | ---------------- | ---------------------- |
| `D[f,x]`       | 对`x`求一阶导数  | `D[E^x Sin[x], x]`     |
| `D[f,{x,n}]`   | 对`x`求 n 阶导数 | `D[E^x Sin[x], {x,2}]` |
| `D[f,x,y,...]` | 依次求偏导       |                        |
| `Dt[f,x]`      | 求微分           |                        |

