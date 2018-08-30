---
layout: post
title: "Python：提取array或list中所有重复出现2次的数"
date: 2018-08-30
tag: Python
---

## 若给定一个较大数组array或列表list，如何提取其中重复出现某一次数的所有元素。

具体问题如下：给定数组

`num = array([1,2,3,3,4,5,6,6,...,499,499])`

如何提起重复出现2次的所有元素，放在一个数组中？

### 1. 使用filter 函数

```Python
cornerList = np.unique(list(filter(lambda x:num.count(x)==2,num)))
```

### 2. 使用列表解析

```Python
a = [x for x in num if num.count(x)==2]
cornerList = np.unique(a)
```

### 3. 使用生成器

```Python
 a = (x for x in num if num.count(x)==2)
 b=[]
 for i in a: 
     b.append(i)
 cornerList = np.unique(b)
```

### 区别：
- 生成器表达式是在python2.4中引入的，当序列过长， 而每次只需要获取一个元素时，应当考虑使用 **生成器** 表达式而不是列表解析
- 生成器表达式的语法和列表解析一样，只不过生成器表达式是被（）括起来的，而列表解析是[]
- 当需要只是执行一个循环的时候尽量使用循环而不是列表解析，这样更符合python提倡的直观性
```Python
for i in range(10):
    print i
```
- 列表解析的性能相比要比map要好，实现相同功能的for循环效率最差（和列表解析相比差两倍）
- 列表解析可以转换为 for循环或者使用map（其中可能会用到filter、lambda函数）表达式，但是列表解析更为简单明了，后者会带来更复杂和深层的嵌套

- 当数据量大，需要遍历每个元素时，为了提升速度，推荐优先级：
> 生成器\> 列表解析 \> filter函数 \> for循环
