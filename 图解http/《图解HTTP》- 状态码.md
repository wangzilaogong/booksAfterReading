# 《图解HTTP》— 返回结果的HTTP状态码

 	状态码简单来说就是服务器对于HTTP请求的返回结果，我们先大体上对状态码有一个大体了解。

| 返回值  | 类别      | 原因短语                |
| ---- | ------- | ------------------- |
| 1XX  | 信息状态码   | 接收的请求正在处理           |
| 2XX  | Success | 请求处理完成且成功           |
| 3XX  | 重定向     | 需要进行附加操作完成请求        |
| 4XX  | 客户端错误   | 服务器无法处理请求，一般都是客户端错误 |
| 5XX  | 服务器错误   | 服务器处理错误             |

* 200  正常处理	
* 204 No Content  处理成功，没有资源可以返回。
* 206 Partial Content 处理成功且返回一部分资源。
* 301 Moved Permanly 永久重定向  更新书签
* 302 Found  临时性重定向 不更新书签但是保存书签
* 303 see other 表示请求的资源有另一个URI
* 304 Not Modified  表示客户端发送带条件的请求，服务器允许访问资源但是条件不符合，返回304时无主体。
* 307 Temporary Redirect 临时重定向
* 400 Bad Request 请求出错
* 401 Unauthorized 没授权的
* 403 Forbidden 拒绝访问那个资源
* 404 Not Found 无资源
* 500 服务器错误
* 503 无法处理请求

前端漫漫路还在一个人苦苦学习？快点加moomoocode，这里好多小伙伴再等着你。

![](http://oydcisax6.bkt.clouddn.com/20171103230008_oYXQb1_Screenshot.jpeg)



 