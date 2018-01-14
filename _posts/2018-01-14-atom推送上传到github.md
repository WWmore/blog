---
layout: post
title: "atom push to github"
date: 2018-01-14
description: "解决 atom 编辑好如何上传push到github上"
tag: github
---

已经修改过的文件，点击atom右下角的push 没有任何反应怎么办？ github个人主页上也没有同步更新怎么办？

参考 http://blog.csdn.net/mishifangxiangdefeng/article/details/53308343 中的介绍

在atom右边栏 git 中 stage changes 选中修改过的文件，然后在下面的 comment内容里 输入如下内容：

git remote -v
origin  https://github.com/windmissing/windmissing.github.io.git (fetch)
origin  https://github.com/windmissing/windmissing.github.io.git (push)

git remote rm origin

git remote add origin git@github.com:windmissi
ng/windmissing.github.io.git

git remote -v
origin  git@github.com:windmissing/windmissing.github.io.git (fetch)
origin  git@github.com:windmissing/windmissing.github.io.git (push)



之后就会发现，右下角的 ‘PUSH’ 出现了上升的箭头，即点击，同步更新，github上就可以看到刚刚更新的文件，等一会刷新个人博客，则看到更新了的内容~
