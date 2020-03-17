---
title: Request库
summary: 小规模网络爬虫Python第三方库
date: "2020-03-02T00:00:00Z"
tags: ["Scraping"]
reading_time: false  # Show estimated reading time?
share: false  # Show social sharing links?
profile: false  # Show author profile?
comments: false  # Show comments?
# Optional header image (relative to `static/img/` folder).
header:
  caption: ""
  image: ""
---
## Request库

### Response对象的属性

{{< figure library="true" src="RequestFeature.jpg" title="Response对象的属性" lightbox="true" >}}

### 爬取代码的通用代码框架

```python
import requests


def getHTMLText(url):
    try:
        r = requests.get(url, timeout=30)
        r.raise_for_status()
        r.encoding = r.apparent_encoding
        return r.text
    except:
        return "访问错误"


if __name__ == "__main__":
    url = "http://www.baidu.com"
    print(getHTMLText(url))
```

### **kwargs参数

* `params`：字典或字节序列，作为参数添加到url中（后接`?key1=value1&key2=value2`）
* `data`：数据
* `json`：JSON格式的数据
* `headers`：字典，HTTP定制头
* `cookies`：字典或CookieJar
* `auth`：元组，支持HTTP认证功能
* `files`：字典（键为`file`；值为用`open()`函数打开的文件对象），传输文件
* `timeout`：设定超时时间，单位为秒
* `proxies`：字典，设定代理服务器