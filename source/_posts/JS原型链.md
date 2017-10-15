---
title: JS原型链
date: 2017-3-14 08:06:06
tags:
---

## 原型链类

- 创建对象有几种方法
- 原型, 构造函数, 实例, 原型链
- instanceof 的原理
- new 运算符

### 创建对象的方法

- 对象字面量
- new 构造函数
- Object.create

```javascript
// javascript 对象字面量
var o1 = {name: xzzzzz};
var o2 = new Object({name: 'o2'});

// new 构造函数
var Constructor = function() {
    this.name = 'xzzzzz'
};
var o3 = new Constructor();

// Object.create
var p = {name: 'xzzzzz'};
var o4 = Object.create(p);
```

### 原型, 构造函数, 实例, 原型链
关系如下图:

![原型, 构造函数, 实例](https://ws4.sinaimg.cn/large/006tKfTcly1fkimbsoz73j30ge0e83z8.jpg)