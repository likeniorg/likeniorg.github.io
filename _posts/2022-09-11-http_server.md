---
title: 
categories: [Go]
tags: [struct]     # TAG names should always be lowercase
---

## 源码解读

```go
// 定义响应 HTTP 请求的处理器接口
type Handler interface {
    ServeHTTP(ResponseWriter, *Request)
}

// HTTP处理器使用 ResponseWriter 接口去构造一个HTTP响应
type ResponseWriter interface {
    // Set-Response Header
    Header() Header
    // Write 将数据作为HTTP回复的一部分写入连接
    Write([]byte) (int, error)
    // 状态码
    WriteHeader(statusCode int)
 
}
