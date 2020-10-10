---
layout: post
title: "Python：dictionary字典表示"
date: 2018-10-23
tag: Python
---


list 转 dictionary 链接<https://www.jianshu.com/p/fbf71e6da515>

```Python
a=np.arange(20)

b=-np.arange(20)

dict(zip(a,b))
Out: 
{0: 0,
 1: -1,
 2: -2,
 3: -3,
 4: -4,
 5: -5,
 6: -6,
 7: -7,
 8: -8,
 9: -9,
 10: -10,
 11: -11,
 12: -12,
 13: -13,
 14: -14,
 15: -15,
 16: -16,
 17: -17,
 18: -18,
 19: -19}

c=dict(zip(a,b))

c.keys()
Out: [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19]

c.values()
Out: 
[0,
 -1,
 -2,
 -3,
 -4,
 -5,
 -6,
 -7,
 -8,
 -9,
 -10,
 -11,
 -12,
 -13,
 -14,
 -15,
 -16,
 -17,
 -18,
 -19]
```


如果两个list都很大，你需要引入itertools.izip来解决问题:

```Python
import itertools

{k:v for k,v in itertools.izip(a,b)}
Out: 
{0: 0,
 1: -1,
 2: -2,
 3: -3,
 4: -4,
 5: -5,
 6: -6,
 7: -7,
 8: -8,
 9: -9,
 10: -10,
 11: -11,
 12: -12,
 13: -13,
 14: -14,
 15: -15,
 16: -16,
 17: -17,
 18: -18,
 19: -19}
```

```Python
dict = (itertools.izip(a,b))

dict
Out: <itertools.izip at 0x3505f388>

for i in dict:print i
(0, 0)
(1, -1)
(2, -2)
(3, -3)
(4, -4)
(5, -5)
(6, -6)
(7, -7)
(8, -8)
(9, -9)
(10, -10)
(11, -11)
(12, -12)
(13, -13)
(14, -14)
(15, -15)
(16, -16)
(17, -17)
(18, -18)
(19, -19)

```

遍历字典中的元素：
```python
for i, v in newdic.items():
   print i, v
0 [2, 2, 2]
1 [2, 2]
2 [2, 2, 0]
3 [2, 1]
4 [2, 2]
5 [2, 2, 2]
6 [2, 2, 2]
```
