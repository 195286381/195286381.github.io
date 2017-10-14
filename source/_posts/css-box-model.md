---
title: CSS 盒模型
date: 2017-10-14 12:11:25
tags:
---
## CSS盒模型
之前的工作一直都在学习新的东西,疏于整理知识点,现在把CSS盒模型系统的整理一下:

大致有如下几点:

- 基本概念: 标准模型 + IE模型
- 标准模型和IE模型的区别 (计算高度和宽度的不同)
- CSS如何设置这两种模型 (box-sizing)
- JS如何获取盒模型对应的宽和高
- 根据盒模型解释边距重叠
- BFC (边距重叠解决方案)

### 基本概念
**盒模型**组成: margin + border + padding + content

### 标准模型和IE模型的区别
标准模型的 width/height 等于 content 的 width/height
IE模型的 width/height 等于 content+padding+border 的 width/height
### CSS盒模型设置
```css 
    box-sizing: content-box; // 标准模型
    box-sizing: border-box; // IE 模型
```