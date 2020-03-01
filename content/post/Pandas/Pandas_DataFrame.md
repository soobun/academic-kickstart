---
title: Pandas之DataFrame
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
## 生成DataFrame


```
import pandas as pd
import numpy as np
```


```
d1=pd.DataFrame(np.arange(10).reshape((2,5))) #自动生成索引
d1
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>0</th>
      <th>1</th>
      <th>2</th>
      <th>3</th>
      <th>4</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0</td>
      <td>1</td>
      <td>2</td>
      <td>3</td>
      <td>4</td>
    </tr>
    <tr>
      <th>1</th>
      <td>5</td>
      <td>6</td>
      <td>7</td>
      <td>8</td>
      <td>9</td>
    </tr>
  </tbody>
</table>
</div>




```
dict={"one":pd.Series([1,2,3],index=['a','b','c']),
   "two":pd.Series([4,5,6,7],index=['a','b','c','d'])}
d2=pd.DataFrame(dict)   #由字典生成，字典的键名为列名
d2
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>one</th>
      <th>two</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>a</th>
      <td>1.0</td>
      <td>4</td>
    </tr>
    <tr>
      <th>b</th>
      <td>2.0</td>
      <td>5</td>
    </tr>
    <tr>
      <th>c</th>
      <td>3.0</td>
      <td>6</td>
    </tr>
    <tr>
      <th>d</th>
      <td>NaN</td>
      <td>7</td>
    </tr>
  </tbody>
</table>
</div>




```
d3=pd.DataFrame(dict,index=['b','c','d'],columns=['two','three']) #自由组合
d3
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>two</th>
      <th>three</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>b</th>
      <td>5</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>c</th>
      <td>6</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>d</th>
      <td>7</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>



示例：将表格转换为DataFrame

|城市|环比|同比|定基|
|---|---|---|---|
|北京|101.5|120.7|121.4|
|上海|101.2|127.3|127.8|
|广州|101.3|119.4|120.0|
|深圳|102.0|140.9|145.5|



```
city={"环比":[101.5,101.2,101.3,102.0],"同比":[120.7,127.3,119.4,140.9],"定基":[121.4,127.8,120.0,145.5]}
d4=pd.DataFrame(city,index=["北京","上海","广州","深圳"])
d4
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>环比</th>
      <th>同比</th>
      <th>定基</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>北京</th>
      <td>101.5</td>
      <td>120.7</td>
      <td>121.4</td>
    </tr>
    <tr>
      <th>上海</th>
      <td>101.2</td>
      <td>127.3</td>
      <td>127.8</td>
    </tr>
    <tr>
      <th>广州</th>
      <td>101.3</td>
      <td>119.4</td>
      <td>120.0</td>
    </tr>
    <tr>
      <th>深圳</th>
      <td>102.0</td>
      <td>140.9</td>
      <td>145.5</td>
    </tr>
  </tbody>
</table>
</div>




```
d4['环比']  #获取某一列
```




    北京    101.5
    上海    101.2
    广州    101.3
    深圳    102.0
    Name: 环比, dtype: float64




```
d4.loc['上海'] #获取某一行用.loc[index]
```




    环比    101.2
    同比    127.3
    定基    127.8
    Name: 上海, dtype: float64



## 重新索引（reindex()方法）


```
d4=d4.reindex(index=['北京',"上海","深圳","广州"])
d4
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>环比</th>
      <th>同比</th>
      <th>定基</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>北京</th>
      <td>101.5</td>
      <td>120.7</td>
      <td>121.4</td>
    </tr>
    <tr>
      <th>上海</th>
      <td>101.2</td>
      <td>127.3</td>
      <td>127.8</td>
    </tr>
    <tr>
      <th>深圳</th>
      <td>102.0</td>
      <td>140.9</td>
      <td>145.5</td>
    </tr>
    <tr>
      <th>广州</th>
      <td>101.3</td>
      <td>119.4</td>
      <td>120.0</td>
    </tr>
  </tbody>
</table>
</div>




```
d4=d4.reindex(columns=['同比','环比','定基'])
d4
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>同比</th>
      <th>环比</th>
      <th>定基</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>北京</th>
      <td>120.7</td>
      <td>101.5</td>
      <td>121.4</td>
    </tr>
    <tr>
      <th>上海</th>
      <td>127.3</td>
      <td>101.2</td>
      <td>127.8</td>
    </tr>
    <tr>
      <th>深圳</th>
      <td>140.9</td>
      <td>102.0</td>
      <td>145.5</td>
    </tr>
    <tr>
      <th>广州</th>
      <td>119.4</td>
      <td>101.3</td>
      <td>120.0</td>
    </tr>
  </tbody>
</table>
</div>



> `fill_value`参数：填充缺失位置的值
### 添加/删除列



```
c2=d4.columns.insert(4,'新增列')
d4=d4.reindex(columns=c2,fill_value=0)
d4
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>同比</th>
      <th>环比</th>
      <th>定基</th>
      <th>新增列</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>北京</th>
      <td>120.7</td>
      <td>101.5</td>
      <td>121.4</td>
      <td>0</td>
    </tr>
    <tr>
      <th>上海</th>
      <td>127.3</td>
      <td>101.2</td>
      <td>127.8</td>
      <td>0</td>
    </tr>
    <tr>
      <th>深圳</th>
      <td>140.9</td>
      <td>102.0</td>
      <td>145.5</td>
      <td>0</td>
    </tr>
    <tr>
      <th>广州</th>
      <td>119.4</td>
      <td>101.3</td>
      <td>120.0</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
</div>




```
d4.drop('新增列',axis=1)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>同比</th>
      <th>环比</th>
      <th>定基</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>北京</th>
      <td>120.7</td>
      <td>101.5</td>
      <td>121.4</td>
    </tr>
    <tr>
      <th>上海</th>
      <td>127.3</td>
      <td>101.2</td>
      <td>127.8</td>
    </tr>
    <tr>
      <th>深圳</th>
      <td>140.9</td>
      <td>102.0</td>
      <td>145.5</td>
    </tr>
    <tr>
      <th>广州</th>
      <td>119.4</td>
      <td>101.3</td>
      <td>120.0</td>
    </tr>
  </tbody>
</table>
</div>


