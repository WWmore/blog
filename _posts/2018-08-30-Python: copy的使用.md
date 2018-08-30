---
layout: post
title: "Python：copy的使用"
date: 2018-08-30
tag: Python
---

### 数组np.array的copy
```Python
np.copy 
```

### 列表list的copy
>  Python中的对象之间赋值时是按引用传递的，如果需要拷贝对象，需要使用标准库中的copy模块。

> 
1. copy.copy 浅拷贝 只拷贝父对象，不会拷贝对象的内部的子对象。
2. copy.deepcopy 深拷贝 拷贝对象及其子对象

```Python
>>> import copy
>>> a = [1,2,3,4,['a','b']]           # 原始对象
>>> b = a                             # 赋值，传对象的引用
>>> c = copy.copy(a)                  # 浅copy
>>> d = copy.deepcopy(a)              # 深copy
>>> a.append(5)
>>> a[4].append('c')
>>> print 'a=',a
a= [1, 2, 3, 4, ['a', 'b', 'c'], 5]   # 内外层数据均修改
>>> print 'b=',b
b= [1, 2, 3, 4, ['a', 'b', 'c'], 5]   # 内外层数据均修改
>>> print 'c=',c
c= [1, 2, 3, 4, ['a', 'b', 'c']]      # 浅copy，内层数据被修改
>>> print 'd=',d
d= [1, 2, 3, 4, ['a', 'b']]           # 深copy，均不受影响
```
