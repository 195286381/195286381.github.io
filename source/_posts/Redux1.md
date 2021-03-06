---
layout: folder
title: React&Redux(1) Why Redux?
date: 2017-8-16 10:50:30
tags: Redux
---
# why Redux ?

## What's Redux/ Why does it exisit?

### Redux is All About State Management
每当我们学习一个新的工具时,我们要理解为什么我们需要 Redux ? 下面我们将要给出答案.

**Redux is All About State Management** - Redux 就是关于状态管理的

Redux 的官方文档对其是这样描述的:

***a predicatable container for javascript apps***

那么你可能会好奇: 为什么 React 已经管理了前端状态, 那么为什么我们还需要 Redux ?

使用 Redux 的好处体现在当你在处理如两个组件共享同一个状态时, 这中两个组件都需要访问同一个状态时的场景, 我们叫做 **状态共享** ,
你可以通过状态提升如提升状态到最近的父组件来实现状态共享, 但是,如果更多的组件需要共享同一个状态, 你需要一层一层的把状态提升到父组件, 这种操作是相当乏味的. 并且, 在状态提升的过程中, 有很多中间组件并不需要或者这个状态.

当构建Web应用时, Redux 不仅提供了一个组织数据存储的方式,也提供了在应用内快速访问数据的方式. 告诉 Redux 那个组件需要那个数据, Redux 将负责剩下的工作.

使用 Redux, 你就是在控制 `什么时候`, `为什么`, `怎么` 操作状态.

### The Store: A Single Source of Truth

Redux 的一个根本原则就是单一数据源: The store, 
store 对象 包含了应用的所有全局状态, 全部被维护在一个对象树上.

只有一个单独的状态树能获益很多方面, 集中式的定位,调试和审查代码也都将变得更加直接.

为了保证单一数据源, Redux 也实现了一些规则来作为保证, 其中一点: 状态在 Redux 中是 `read-only`, 也就是说, Redux的状态是不可变的, 我们不能直接修改 Redux 的状态, 而是声明一种去改变状态的意图.

最终证明发现, 只有叫做 reducers 的纯函数有能力改变 状态.

总结来说, Redux 的**三大原则** :
- 单一数据源
- 状态不可变
- 状态修改由纯函数完成

单页应用时使前端开发变得越来越复杂, 选择合适的状态管理工具, 比之前而言越来越重要, 除了管理一些表格状态, 一个应用程序也需要管理其他的状态:

- 服务端响应
- 缓存数据
- 本地数据

再加之,目前的UI状态也变得越来越复杂,我们还需要追踪:
- 激活的路由
- 当前选中的tab标签
- 导航控制

### summary
Redux 是一个用于前端状态管理的 Javascript 库, 他与 React 应用无关, 随着应用程序的复杂, 来自状态方便的 bug 越来越多, 使用 Redux 管理一个单一状态树, 使得状态更加 `predictability`, 这也是为什么开发者喜欢 Redux 的原因.

## How Redux Improves Predictability?

既然说到 Redux 提升状态的可预测性, 那么它是在那几个方面提升状态的可预测性呢?

### Predictability
Redux 提高应用的可预测性在如下几个方面.

- 数据集中化到一个地方: `store`
- 组件不能直接从 store 写数据
- 数据在 store 的流向是单向的
- 严格限制 store 的修改

Unidirectional Data Flow Review

回顾 React 的核心特性是 `单向数据流`

![](https://ws3.sinaimg.cn/large/006tNc79ly1fkiy4v4deqj31kw0w0dp6.jpg)
`Data flows down from parent component to child component. Data updates are sent to the parent component where the parent performs the actual change.`

React 的单向数据流工作的很好, 但是问题来自深层嵌套的数据结构:

![](https://ws1.sinaimg.cn/large/006tNc79ly1fkiye8kxdbj31hc0u0myv.jpg)

在深层嵌套的结构中,组件状态从父组件传递途径中间组件最后才到目标组件.

### Summary

Redux 在以下几个方面改善可预测性:

- 集中数据到一个地方: store
- 组件获取数据必须发送请求
- 数据单向的流动
- 严格限制状态的改变

Redux 也采用了 React 的思想, 采用 `单向数据流`.
 
---

# todo (待补充....)
## Redux Stores VS Component State
 Redux 状态 VS 组件状态
## Pure Functions
纯函数

## Array's.reduce() Method
reduce方法在redux中的应用