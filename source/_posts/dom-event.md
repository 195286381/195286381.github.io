---
title: 前端知识梳理-DOM事件类
date: 2017-10-02 15:34:46
tags:
---

## DOM事件类
- 基本概念: DOM 事件的级别
- DOM 事件模型 (捕获/冒泡)
- DOM 事件捕获的具体流程
- Event 对象的常见应用
- 自定义事件

### DOM 事件级别
- DOM0
    +  element.onclick = function() {}
- DOM2
    + element.addEventListener('click', function() {})
- DOM3
    + element.addEventListenr('keyup', function() {})

### DOM 事件模式
- 事件捕获
- 事件冒泡

### 事件捕获的具体流程
一个完成的事件流分三个阶段:
1. 事件捕获阶段 (从最不具体的到具体) (window -> document -> html -> body -> ....)
2. 处于目标阶段 
3. 事件冒泡阶段 (从最具体到最不具体)

### Event 对象的常见应用
- 阻止默认行为 event.preventDefault()
- 阻止冒泡 event.stopPropagation()
- 阻止事件的响应优先级 event.stopImmediateProppagation
- event.currentTarget // 事件当前所处于的元素
- event.target // 触发事件的元素

### 自定义事件
```javascript
    var eve = new Event('custome');
    ev.addEventListener('custome', function() {
        con;sole.log('custome')
        });
    ev.dispatchEvent(eve);
```