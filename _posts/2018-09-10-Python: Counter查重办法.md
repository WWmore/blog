---
layout: post
title: "Python：Python: Counter查重办法"
date: 2018-09-10
tag: Python
---

### counter

```Python
>>> from collections import Counter
>>> c = Counter('abcasd')
>>> c
Counter({'a': 2, 'c': 1, 'b': 1, 's': 1, 'd': 1})
```

## 常见做法:

```Python
sum(c.values())                 # 继承自字典的.values()方法返回values的列表，再求和

c.clear()                       # 继承自字典的.clear()方法，清空counter

list(c)                         # 返回key组成的list

set(c)                          # 返回key组成的set

dict(c)                         # 转化成字典

c.items()                       # 转化成(元素，计数值)组成的列表

Counter(dict(list_of_pairs))    # 从(元素，计数值)组成的列表转化成Counter

c.most_common()[:-n-1:-1]       # 最小n个计数的(元素，计数值)组成的列表

c += Counter()                  # 利用counter的相加来去除负值和0的值
```
