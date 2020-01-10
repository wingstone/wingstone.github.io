---
layout: post
title: ShaderToy Idea
author: wingstone
---

记录阅读ShaderToy过程中，所遇到的好的想法，以及tricks~

 - bloom类似效果的实现，在已知距离场的情况下，使用距离的倒数能渲染出接近bloom的效果
 - 使用worlay noise的思想，可以更好的渲染大量粒子的实现，只需要保证每个粒子运动范围在局部栅格空间即可；当然局部空间越接近全屏，粒子模拟效果越好~
局部空间为全屏即为最原始的再屏幕空间遍历所有的粒子；