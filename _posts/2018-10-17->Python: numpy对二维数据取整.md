---
layout: post
title: "Python: numpy对二维数据取整"
date: 2018-10-17
tag: Python
---

链接： <http://sofasofa.io/forum_main_post.php?postid=1001175>

```Python
>>> x
array([[ 1. ,  2.3],
       [ 1.3,  2.9]])
>>> a = np.trunc(x)
>>> a
array([[ 1.,  2.],
       [ 1.,  2.]])
>>> b = np.ceil(x)
>>> b
array([[ 1.,  3.],
       [ 2.,  3.]])
>>> c = np.floor(x)
>>> c
array([[ 1.,  2.],
       [ 1.,  2.]])
>>> d = np.rint(x)
>>> d
array([[ 1.,  2.],
       [ 1.,  3.]])
``` 
 
 
```Python       
x = np.array([-1.01, 1]）
np.rint(x) 
>>> np.array([-1, 1]）

x = [-0.99, 1]
np.rint(x) 
>>> np.array([-1, 1])
```
