---
layout: post
title: "Matlab：affine registration 散点仿射匹配问题"
date: 2018-02-25
tag: GeometryProcessing 作业
---
给定空间中对应的两组点$\{p_i\}$, $\{q_i\}$, 找到仿射变换$x\to a+Rx$使得$\sum w_i\|a+Rp_i-q_i\|$极小：
 - 推导相应的线性系统；
 - 画出输入点集$\{p_i\}$, $\{q_i\}$，和优化变换后的点集$\{a+Rp_i\}$。

![](/images/posts/gp_homework/12fig_points.jpg)
![](/images/posts/gp_homework/12fig_affine.jpg)
