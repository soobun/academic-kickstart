---
title: 其他图像示例
summary: 其他图像示例
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

## 其他图像示例



```
import matplotlib.pyplot as plt
import numpy as np

labels=['Frogs','Hogs','Dogs','Logs']
sizes=[15,30,45,10]
explode=(0,0.1,0,0)
plt.pie(sizes,explode=explode,labels=labels,autopct='%1.1f%%',shadow=False,startangle=90)
plt.show()
```


{{< figure library="true" src="Matplotlib_Pie.png" title="Pie" lightbox="true" >}}



```
mu,sigma=500,70
a=np.random.normal(mu,sigma,5000)
plt.hist(a,150,normed=0,histtype='stepfilled',alpha=0.75)
plt.show()
```



{{< figure library="true" src="Matplotlib_Hist.png" title="Histogram" lightbox="true" >}}



```
plt.plot(10*np.random.randn(100),10*np.random.randn(100),'o')
plt.show()
```


{{< figure library="true" src="Matplotlib_Scatter.png" title="Scatter Point" lightbox="true" >}}

