---
layout: post
title: "Python：numpy数组拼接、合并"
date: 2018-10-02
tag: Python
---

链接： <https://blog.csdn.net/zyl1042635242/article/details/43162031>

### 列表list可以使用append（）， extend（）进行拼接、合并


### numpy数组array，可以使用np.append(), np.vstack, np.hstack, np.concatenate((a, b), axis=0/1)进行


> numpy提供了numpy.concatenate((a1,a2,...), axis=0)函数。能够一次完成多个数组的拼接。其中a1,a2,...是数组类型的参数
示例：

```Python
a=np.array([1,2,3])
b=np.array([11,22,33])
c=np.array([44,55,66])
np.concatenate((a,b,c),axis=0)  # 默认情况下，axis=0可以不写
array([ 1,  2,  3, 11, 22, 33, 44, 55, 66]) #对于一维数组拼接，axis的值不影响最后的结果
```

```Python
a=np.array([[1,2,3],[4,5,6]])
b=np.array([[11,21,31],[7,8,9]])
np.concatenate((a,b),axis=0)
array([[ 1,  2,  3],
       [ 4,  5,  6],
       [11, 21, 31],
       [ 7,  8,  9]])
np.concatenate((a,b),axis=1)  #axis=1表示对应行的数组进行拼接
array([[ 1,  2,  3, 11, 21, 31],
       [ 4,  5,  6,  7,  8,  9]])
```       

### 数据量大时，运行时间对比：concatenate效率最高

```Python
import numpy as np

from time import clock as now

a=np.arange(9999)
b=np.arange(9999)
time1=now()
c=np.concatenate((a,b),axis=0)
time2=now()
print time2-time1
9.61267735811e-05
```

```Python
a=np.arange(9999)
b=np.arange(9999)
time1=now()
c=np.append(a,b)
time2=now()
print time2-time1
9.78331660121e-05
```

```Python
a=np.arange(9999)
b=np.arange(9999)
time1=now()
c=np.hstack((a,b))
time2=now()
print time2-time1
0.000101245950873
```


### 数据量小时，运行时间对比：hstack（（））效率最高
```Python
a=np.array([1,2,3])
b=np.array([11,22,33])
time1=now()
c=np.vstack((a,b))
time2=now()
print time2-time1
9.72643683781e-05

```


```Python
a=np.array([1,2,3])
b=np.array([11,22,33])
time1=now()
c=np.hstack((a,b))
time2=now()
print time2-time1
7.90628491814e-05

```

```Python

a=np.array([1,2,3])
b=np.array([11,22,33])
time1=now()
c=np.concatenate((a,b))
time2=now()
print time2-time1
8.13380390809e-05
```

```Python
a=np.array([1,2,3])
b=np.array([11,22,33])
time1=now()
c=np.concatenate((a,b)).reshape((-1,3))
time2=now()
print time2-time1
0.000101245950873

```
