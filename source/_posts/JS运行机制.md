---
title: JS运行机制
date: 2017-5-10 14:06:06
tags:
---

## JS 运行机制

### 单线程
JS 是单线程的.基于异步任务队列的, 一个时间之内只能干一件事情.
```javascript
console.log(1)
// 异步任务要挂起,即使延迟是0
setTimeout(function() {
    console.log(3);
}, 0)
console.log(2)

// output: 1 3 2
```

```javascript
for (var i = 0; i < 4; i++) {
    setTimeout(function() {
        console.log(i);
    }, 1000);
}

// output: 3 3 3 3
```

### (异步)任务队列 和 Event Loop

- setTimeout 和 setInterval
- DOM 事件
- ES6 中的 Promise

### 总结

- 理解JS的单线程的概念
- 理解任务队列
- 理解 Event Loop
- 理解那些语句会放入异步任务队列
- 理解语句放入异步任务队列的时机