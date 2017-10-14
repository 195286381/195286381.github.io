---
title: http-protocal
date: 2017-10-01 16:49:27
tags: http协议 tcp/ip
---


## HTTP 协议类

### HTTP 协议的主要特点

- 简单快速
- 灵活
- 无连接
- 无状态

### HTTP 报文的组成部分

- 请求报文
    + 请求行
    + 请求头
    + 空行
    + 请求体
- 响应报文
    + 状态行
    + 响应头
    + 空行
    + 响应体

### HTTP 方法

- GET -> 获取资源
- POST -> 传输资源
- PUT -> 更新资源
- DELETE -> 

POST 和 GET 的区别
- GET 在浏览器回退时是无害的, 而 POST 会再次提交请求
- GET 产生的URL地址可以被收藏, 而 POST 不可以
- GET 请求会被浏览器主动缓存, 而 POST 不会, 除非手动设置
- GET 只能进行 URL 编码, 而 POST 支持多种编码方式
- GET 请求参数会被完成保存在浏览器历史记录里面, 而 POST 中的参数不会被保留
- GET 请求在 URL 中传送的参数是有长度限制的, 而 POST 没有限制
- 对参数的数据类型, GET只接受 ASCII 字符, 而POST没有限制
- GET 比 POST 更不安全, 因为参数直接暴露在URL上, 所以不能用来传递敏感信息
- GET 参数通过 URL 传递, POST 放在 Request body 中
