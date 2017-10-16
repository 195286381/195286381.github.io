---
title: 前端知识梳理-面向对象类
date: 2017-10-15 10:55:48
tags:
---

## 通信类

### 什么是同源策略以及限制

同源策略限制从一个源加载的文档或脚本如何与另一个源的资源进行交互. 这是一个用于隔离潜在恶意文件的关键的安全机制

- Cookie, LocalStorage 和 IndexDB 无法读取
- DOM 无法获取
- AJAX 请求不能发送

### 如何创建 AJAX

- XMLHttpRequest对象的工作流程
- 兼容性问题
- 事件的触发条件

### 跨域通信的几种方式

- JSONP 
- Hash
- postMessage (H5新增)
- WebSocket (不受同源策略限制)
- CORS (可以理解为支持垮与通信的AJAX)

```javascript
    util.jsonp  = function (url, onsuccess, onerror, charset)
```