---
title: 前端知识梳理-CSS盒模型
date: 2017-10-14 12:11:25
tags: CSS
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

```CSS
    box-sizing: content-box; // 标准模型 (浏览器默认的方法)
    box-sizing: border-box; // IE 模型
```

### JS如何获取盒模型对应的宽和高

 ```
 dom.style.width/height // 取出内联样式的宽和高

 dom.currentStyle.width/height // 获取当前的宽度和高度 (only IE)
 window.getComputedStyle(dom).width/height // 取出计算后的宽和高 (兼容 Firefox Chrome)

 dom.getBoundingClientRect().width/height  // 获取元素的四个角,计算能够得到.
 ```

### BFC (边距重叠解决方案)

- BFC 的基本概念
    + 块级格式化上下文
- BFC 的原理 (渲染规则)
    + BFC 这个元素的垂直方向的边距会发生重叠
    + BFC 不会和浮动元素的 box 重叠 (清除浮动)
    + BFC 在页面上是一个独立的容器
    + 计算 BFC 高度的时候, 浮动元素也会参与计算
- 如何创建 BFC 
    + overflow 不为 visible
    + float 不为 none
    + position 不为 static/relative
    + display 为 inline-tabel/tabel相关 
- BFC 的使用场景
(关于BFC 后续会写一篇介绍)
