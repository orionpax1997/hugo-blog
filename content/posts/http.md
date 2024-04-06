---
title: "什么是 HTTP？"
date: 2020-03-14T15:36:54+08:00
categories: ["Development"]
tags: ["Essay"]
---

## HTTP 协议是什么？

HTTP 协议是超文本传输协议的缩写，英文是 Hyper Text Transfer Protocol。它是从 WEB 服务器传输超文本标记语言 (HTML) 到本地浏览器的传送协议。设计 HTTP 最初的目的是为了提供一种发布和接收 HTML 页面的方法。

## HTTP 特点

- HTTP 协议支持客户端 / 服务端模式，也是一种请求 / 响应模式的协议。
- 简单快速：客户向服务器请求服务时，只需传送请求方法和路径。请求方法常用的有 GET、HEAD、POST。
- 灵活：HTTP 允许传输任意类型的数据对象。传输的类型由 Content-Type 加以标记。
- 无连接：限制每次连接只处理一个请求。服务器处理完请求，并收到客户的应答后，即断开连接，但是却不利于客户端与服务器保持会话连接，为了弥补这种不足，产生了两项记录 HTTP 状态的技术，一个叫做 Cookie, 一个叫做 Session。
- 无状态：无状态是指协议对于事务处理没有记忆，后续处理需要前面的信息，则必须重传。

## HTTP 报文组成

### 请求报文

- 请求行：包括请求方法、URL、协议 / 版本
- 请求头 (Request Header)
- 请求正文

![http1](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/http1.3r0zjd3gxek0.webp)

### 响应报文

- 状态行
- 响应头
- 响应正文

![http2](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/http2.rhz1ee2xn9s.webp)

## 常见的请求方法

- GET: 请求指定的页面信息，并返回实体主体。
- POST: 向指定资源提交数据进行处理请求（例如提交表单或者上传文件）。数据被包含在请求体中。POST 请求可能会导致新的资源的建立和 / 或已有资源的修改。
- HEAD: 类似于 GET 请求，只不过返回的响应中没有具体的内容，用于获取报头
- PUT: 从客户端向服务器传送的数据取代指定的文档的内容。
- DELETE: 请求服务器删除指定的页面。

## 常见状态码

- 200 OK - 客户端请求成功
- 301 - 资源（网页等）被永久转移到其它 URL
- 302 - 临时跳转
- 400 Bad Request - 客户端请求有语法错误，不能被服务器所理解
- 401 Unauthorized - 请求未经授权，这个状态代码必须和 WWW-Authenticate 报头域一起使用
- 404 - 请求资源不存在，可能是输入了错误的 URL
- 500 - 服务器内部发生了不可预期的错误
- 503 Server Unavailable - 服务器当前不能处理客户端的请求，一段时间后可能恢复正常。

## URI 和 URL 的区别？

- URI：Uniform Resource Identifier 统一资源标识符
- URL：Uniform Resource Location 统一资源定位符

HTTP 使用统一资源标识符（Uniform Resource Identifiers, URI）来传输数据和建立连接。URI 是用来标示 一个具体的资源的，我们可以通过 URI 知道一个资源是什么。URL 则是用来定位具体的资源的，标示了一个具体的资源位置。互联网上的每个文件都有一个唯一的 URL。

## POST 和 GET 的区别？

- 都包含请求头请求行，POST 多了请求 BODY。
- GET 多用来查询，请求参数放在 URL 中，不会对服务器上的内容产生作用。POST 用来提交，如把账号密码放入 BODY 中。
- GET 是直接添加到 URL 后面的，直接就可以在 URL 中看到内容，而 POST 是放在报文内部的，用户无法直接看到。
- GET 提交的数据长度是有限制的，因为 URL 长度有限制，具体的长度限制视浏览器而定。而 POST 没有。

## HTTPS 和 HTTP 的区别？

- HTTPS 是 HTTP 协议的安全版本，HTTP 协议的数据传输是明文的，是不安全的，HTTPS 使用了 SSL/TLS 协议进行了加密处理。
- HTTP 和 HTTPS 使用连接方式不同，默认端口也不一样，HTTP 是 80，HTTPS 是 443。
- HTTPS 进行了多次握手、安全算法等，传输速度上要比 HTTP 慢。
