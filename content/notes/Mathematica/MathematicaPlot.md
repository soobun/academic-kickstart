---
title: Mathematica绘图
summary: Mathematica绘图
date: "2020-02-20T17:50:00Z"
tags: ["Mathematica"]
reading_time: false  # Show estimated reading time?
share: false  # Show social sharing links?
profile: false  # Show author profile?
comments: false  # Show comments?
# Optional header image (relative to `static/img/` folder).
header:
  caption: ""
  image: ""
---

## 常用平面图像绘图命令

| 命令             | 功能           | 例子                                                         |
| ---------------- | -------------- | ------------------------------------------------------------ |
| `Plot`           | 显函数绘图     | `Plot[x*Sin[1/x],{x,-1,1}]`                                  |
| `ParametricPlot` | 参数方程绘图   |                                                              |
| `PolarPlot`      | 极坐标方程绘图 |                                                              |
| `ContourPlot`    | 隐函数绘图     | `ContourPlot[x*y*(x^2 - y^2) == 2, {x, -10, 10}, {y, -10, 10}]` |
| `ListPlot`       | 绘制点列图     |                                                              |

## 常用的三维图形绘制命令

### Plot3D 绘制二元函数对应的空间曲面

`Plot3D[x*y*(x^2-y^2),{x,-10,10},{y,-10,10}]`

{{< figure library="true" src="Plot3D.jpg" title="An example" lightbox="true" >}}

### ParametricPlot3D 绘制空间曲线、曲面参数方程对应空间曲线与曲面