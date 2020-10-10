---
layout: post
title: "Python： Counter、count查重办法"
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

链接<https://gist.github.com/Nataila/7653082>

获取list中的重复元素以及其个数:
```Python
mylist = [2,2,2,2,2,2,3,3,3,3]
mylist.sort()
myset = set(mylist)

for item in myset:
    print mylist.count(item), " of ", item, " in list"
6  of  2  in list
4  of  3  in list
```

```Python
count = {}
for item in mylist:
      count[item] = mylist.count(item)

count
Out: {2: 6, 3: 4}
```

链接<https://blog.csdn.net/ftell/article/details/79455932>

显示重复元素及其个数：

```Python
a = [1, 2, 3, 2, 1, 5, 6, 5, 5, 5]
b = set(a)
for each_b in b:
    count = 0
    for each_a in a:
        if each_b == each_a:
            count += 1
    print(each_b, ": ", count)
    
(1, ': ', 2)
(2, ': ', 2)
(3, ': ', 1)
(5, ': ', 4)
(6, ': ', 1)
```

列出重复元素的索引:
```Python
a = [1, 2, 3, 2, 1, 5, 6, 5, 5, 5]
source = a
from collections import defaultdict
def list_duplicates(seq):
    tally = defaultdict(list)
    for i,item in enumerate(seq):
        tally[item].append(i)
    return ((key,locs) for key,locs in tally.items() 
                            if len(locs)>1)
 
for dup in sorted(list_duplicates(source)):
    print(dup)

(1, [0, 4])
(2, [1, 3])
(5, [5, 7, 8, 9])
```
