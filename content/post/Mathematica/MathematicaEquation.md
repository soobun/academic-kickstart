---
title: 解方程组和不等式
summary: 解方程组和不等式
date: "2020-02-20T00:00:00Z"
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

## 解方程组和不等式
```mathematica
Solve[x^2-y^3==1,x]
>>>{{x -> -Sqrt[1 + y^3]}, {x -> Sqrt[1 + y^3]}}
{x1,x2}=x/.%
>>>{-Sqrt[1 + y^3], Sqrt[1 + y^3]}

Reduce[x^2-2x-2<=0]
>>>1 - Sqrt[3] <= x <= 1 + Sqrt[3]
```

