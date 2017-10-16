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
关系如下图:

![原型, 构造函数, 实例](https://ws4.sinaimg.cn/large/006tKfTcly1fkimbsoz73j30ge0e83z8.jpg)

### instanceof 
就是判断实例的`__proto__`是否跟构造函数的prototype引用的是同一个对象,如果不是则继续往prototype的原型链去找,只要有一个满足引用的是同一个对象则返回true, 否则返回 false.

下面看一个实例, 受保护的构造函数:
```javascript
    /*
     * create by xzzzzz
     */
    function Foo(name, age) {
        // 对构造函数进行保护
        if (!(this instanceof Foo)) {
            return new Foo(arguments);
        }

        this.name = name;
        this.age = age;
        // do something you like

    }

    var foo = Foo(xzzzzz, age)
    console.log(foo.name, foo.age) // output: xzzzzz age
```

### new 运算符
调用 new 运算函数时, 会经历如下步骤:

1. 一个新对象被创建, 它继承自foo.prototype
2. 构造函数 foo 被执行. 执行的时候, 相应的传参会被传入, 同时上下文(this)被会指定为这个新势实例, `new foo` 等同于 `new foo()`, 只能用在不能传递任何参数的情况.
3. 如果构造函数返回了一个"对象", 那么这个对象就会取代整个 new 出来的结果, 如果构造函数没有返回对象, 那么 new 出来的结果为步骤1创建的对象.
