---
title: 前端知识梳理-面向对象类
date: 2017-10-16 10:55:48
tags:
---

## 面向对象类

```javascript

    /**
     * 类的声明
     */
    
    function Foo(name) {
        this.name = name
    }

    /**
     * ES6中的class的声明
     */
    class Animal2 {
        constructor() {
            this.name = name;
        }
    }


    /**
     * 借助构造函数实现继承
     */
    
    function Parent1() {
        this.name = 'Parent1';
    }

    Parent.ptototype.say() {
        console.log(this.name);
    }

    function Child1() {
        Parent1.call(this); // (apply可选) 改变this指向
        this.type = 'Child1';
    }
    // 原理: 改变this指向.
    // 缺点: 构造函数实现继承无法继承原型属性

    /**
     * 借助原型实现继承
     */
    
    function Parent2() {
        this.name = 'Parent2';
        this.play = [1, 2, 3];
    }

    function Child2() {
        this.type = 'Child2';
    }

    Child2.prototype = new Patent2();

    /**
     * 组合继承
     */

     function Parent3() {
         this.name = 'Parent3'
         this.play = [1, 2, 3];
     }

     function Child3() {
         Parent3.call(this);
         this.type = 'Child3'
     }

     Child3.prototype = new Parent3();
     var s3 = new Child3();
     var s4 = new Child3();
     s3.play.push(4);
     console.log(s3.play, s4.play); // output: [1, 2, 3] [1, 2, 3, 4]
     
     // 缺点: 

    /**
     * 组合继承的优化1
     */

    function Parent4() {
        this.name = 'Parent4';
        this.play = [1, 2, 3];
    }

    function Child4() {
        Parent4.call(this);
        this.type = 'Child4'
    }

    Child4.prototype = Parent4.prototype;
    var s5 = new Child4();
    var s6 = new Child4();
    // 缺点:

    ***最终版***

    /**
     * 组合继承的优化2
     */

    function Parent5() {
        this.name = 'Parent5';
        this.play = [1, 2, 3];
    }

    function Child5() {
        Parent5.call(this);
        this.type ='Child5'
    }

    var proto = Object.create(Parent5.prototype);
    proto.constructor = Child5;
    Child5.prototype = proto;

```