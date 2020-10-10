---
layout: post
title: "Matlab：读取obj文件"
date: 2018-02-25
tag: GeometryProcessing 作业
---
使用Matlab函数$[V, T]=readobj(filename)$ 读取obj文件，返回格点集$V$和面集$F$：

 - 使用函数`fopen, frewind, fclose, fgets, strtok, sscanf`
 - obj文件格式参考`https://en.wikipedia.org/wiki/Wavefront_.obj_file`
 - 使用`trimesh`或者`trisurf`展示三角网格

![](/images/posts/gp_homework/13arm_scatter.jpg)
![](/images/posts/gp_homework/13arm_trimesh.jpg)
![](/images/posts/gp_homework/13arm_trisurf.jpg)
![](/images/posts/gp_homework/13arm_patch.jpg)
![](/images/posts/gp_homework/13egea_scatter.jpg)
![](/images/posts/gp_homework/13egea_trimesh.jpg)
![](/images/posts/gp_homework/13egea_trisurf.jpg)
![](/images/posts/gp_homework/13egea_patch.jpg)
