---
layout: post
title: "《GRASSHOPPER PRIMER》整理"
date: 2019-03-09
tag: Rhino
---

这个版本是Grasshopper软件的初级入门版，2009年，中文翻译，有些components已经old。

<img src="/images/posts/Rhino/grasshopper_primer.png" height="30%" width="30%">

前11章很有参考价值，后面12-16章针对想自己编写component的人。

<div align="center">
<img src="/images/posts/Rhino/grasshopper1.png" height="30%" width="30%" alt="bb" >
<img src="/images/posts/Rhino/grasshopper2.png" height="30%" width="30%" alt="cc" >
</div>


## 快捷键：

- 空格： 设置电池 是否运行、是否可见等。
- 左键双击： 调出搜索； 输入数字，显示slider
- ctrl+alt+左击： 显示电池所在位置
- ctrl+连线： 删除连线
- shift+连线： 增加连线
- 双击标题栏，最小化GRASSHOPPER
- 选中Rhino某个/些对象后，Enter/右击，返回到GRASSHOPPER

## Range, Series, Interval

<img src="/images/posts/Rhino/range.png" height="50%" width="50%" alt="bb" >
<img src="/images/posts/Rhino/series.png" height="50%" width="50%" alt="bb" >
<img src="/images/posts/Rhino/interval.png" height="50%" width="50%" alt="bb" >

## Curves

#### 构造螺线spiral
<img src="/images/posts/Rhino/spiral.png" height="50%" width="50%" alt="bb" >

#### 构造sin（三角函数）曲线
<img src="/images/posts/Rhino/sin.png" height="50%" width="50%" alt="bb" >

#### 空间散点曲线插值
<img src="/images/posts/Rhino/curve_ex2.png" height="50%" width="50%" alt="bb" >
注：Polyarc 没有反应

#### 类直纹悬链面线
<img src="/images/posts/Rhino/catenoid_like.png" height="50%" width="50%" alt="bb" >

#### 利用vectors生成圆线\torus面
<img src="/images/posts/Rhino/curve_ex.png" height="50%" width="50%" alt="bb" >





## Surfaces

#### Surface connect 插值三条边界线生成带offset的网格面
<img src="/images/posts/Rhino/offset.png" height="50%" width="50%" alt="bb" >

#### Surface paneling 插值四条曲线生成带指定paneling的网格面
<img src="/images/posts/Rhino/paneling.png" height="50%" width="50%" alt="bb" >

> 我们把这个几何图形连接到Morph Box 运算器，这个几何图形将会被复制到每一个细分区域；
> 我们使用代表Windows 系统的Bounding Box 作为参考几何图形；
> 最后， 我们输入100 个盒子形状的细分区域作为目标盒子的位置来复制几何图形。

#### Surface diagrid 插值两条曲线生成对角网格
<img src="/images/posts/Rhino/diagrid.png" height="50%" width="50%" alt="bb" >
<img src="/images/posts/Rhino/diagrid2.png" height="50%" width="50%" alt="bb" >
注： 上面两个区别在对U方向的细分。


##### Brep的作用

> 因为计算机没有考虑到第三个方向的维度，例如深度或厚度。但如何让Grasshopper 去描述有三个维度的面？McNeel 公司的开发者将这个难题扔给了我们，并创造了第二种方法：建立一个可
以单独控制的物体，就像在Rhino 界面中那样。使用Brep 或边界表示。Brep 可以被当做是一个立体的或者类似于Rhino 中的多边形物体。它还是由众多NURBS 曲面
组成， 但是他们在一起建立一个有厚度的对象，即使理论上NURBS 曲面是没有厚度的。由于Brep 基本上是由面构成的，所以一些基本的NURBS 表面分析运算器还是可以使用的，但还有
一些就不可以了。这是因为Grasshopper 内置的翻译逻辑会尝试将物体转变为所需要的输入形式。如果一个运算器需要一个Brep 但是你给它一个面，那么这个面将被转换成为一个Brep。

> 这个Brep 运算器能够把一个或者一系列Brep 的相关元素，例如面、边缘、顶点等，提取出来使用。在这个实例中，我们想知道一个角点的位置，以便利用这些角点在每个细分区域对这些角点进行对角线连接





---
链接： <a href="https://www.zhihu.com/question/24497860"  target="_blank">建筑师怎样快速学习 Rhino 和 Grasshopper？</a>
