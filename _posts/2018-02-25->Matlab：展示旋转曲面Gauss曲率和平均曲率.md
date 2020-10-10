---
layout: post
title: "Matlab：展示旋转曲面Gauss曲率和平均曲率"
date: 2018-02-25
tag: GeometryProcessing 作业
---

已知旋转曲面
$$ X(u,v)=\begin{array}{c@{}cc}
\left[\begin{array}{ccccc}
 & cos(v) & -sin(v) & 0 & \\
& sin(v) & cos(v) & 0 &\\
 & 0 & 0 & 1 & \\
\end{array}\right]
\end{array}\begin{array}{c@{}cc}
\left[\begin{array}{cc}
 x(u)\\0\\ z(u)\\
\end{array}\right]
\end{array},$$
取$(x(u),z(u)) = (r cos(u)+a, r sin(u)), a >0, r > 0$.

 1. 在$[0, 2\pi]\times[0, 2\pi]$范围内展示曲面X.
 2. 计算Gauss曲率和平均曲率，并在曲面上用颜色展示正(red)负(blue)零(green)曲率值.

![](/images/posts/gp_homework/6Revolution surface.jpg)

![](/images/posts/gp_homework/6Gauss curvature.jpg)

![](/images/posts/gp_homework/6Mean curvature.jpg)

<figure class='half'>
<img scr="{{wwmore.github.io}}/images/posts/gp_homework/6Revolution surface.jpg">
<img scr="{{wwmore.github.io}}/images/posts/gp_homework/6Revolution surface.jpg">
</figure>
