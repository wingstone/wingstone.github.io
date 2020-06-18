---
layout: post
title: Unity Custom UI Mesh
author: wingstone
---

## Unity Custom UI Mesh

unity中继承Graphic类或者MaskableGraphic可以实现自定义UI组件，并且在`protected override void OnPopulateMesh(UI.VertexHelper vh);`函数中可以操作或自定义网格，用于实现各种各样的UI形状；