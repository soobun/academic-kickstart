---
title: 二维曲线
summary: 画连续的二维曲线
date: "2020-02-29T00:00:00Z"
tags: ["Matplotlib"]
reading_time: false  # Show estimated reading time?
share: false  # Show social sharing links?
profile: false  # Show author profile?
comments: false  # Show comments?
# Optional header image (relative to `static/img/` folder).
header:
  caption: ""
  image: ""
---

## 连续图像

保存PNG图像：`plt.savefig('test', dpi=600)`

限定坐标轴范围：`plt.axis([xmin,xmax,ymin,ymax])`

### 曲线风格（linestyle）

| 字符 | 样式   |
| ---- | ------ |
| -    | 实线   |
| --   | 破折线 |
| -.   | 点划线 |
| :    | 虚线   |

### 数据点标记（marker）

| 字符    | 样式              |
| ------- | ----------------- |
| .       | 点                |
| ,       | 极小的点          |
| o       | 实心圆            |
| v ^ < > | 下/上/左/右三角   |
| 1 2 3 4 | 下/上/左/右花三角 |
| s       | 正方形            |
| p       | 五角形            |
| *       | 星形              |
| x       | 叉号              |

标记点颜色`markerfacecolor`

标记点尺寸`markersize`

### 复杂子图

`plt.subplot2grid((Trow,Tcol),(row,col),colspan=2)`（合并两列）