# 《图解HTTP》— 安全的HTTPS

​	**HTTP缺点**

- 不加密的明文消息通信

- 不验证通信的身份，可能伪装

- 无法确定报文的完整性

  ​其实HTTPS其实是SSL和HTTP共同使用组合之称，HTTP over SSL。这种是整体加密的通信线路。还有一种是内容加密，对HTTP协议传输的内容进行加密报文加密。

  ​**不验证通信身份的伪装**

  ​服务器对于任意请求都是响应的，但是不确定对方是不是真实的客户端，无法确保对方是否具有访问权限。还有Dos攻击。

  ​**可能篡改的不完整报文**

  ​不知道如何在发出请求之后进行对其修改。中间人攻击

![](http://oydcisax6.bkt.clouddn.com/20171106214316_g9iLed_Screenshot.jpeg)

​	**HTTP+加密+认证+完整性保护=HTTPS**

![](http://oydcisax6.bkt.clouddn.com/20171106214259_Asi78O_Screenshot.jpeg)

​	HTTPS是身披SSL外壳的HTTP，如图所示相比HTTP多了一层SSL（可以细究下SSL）

![](http://oydcisax6.bkt.clouddn.com/20171106214537_QjkjGy_Screenshot.jpeg)

HTTPS通信步骤

![](http://oydcisax6.bkt.clouddn.com/20171106221218_xA6lcd_Screenshot.jpeg)

![](http://oydcisax6.bkt.clouddn.com/20171106222758_h0Ns76_Screenshot.jpeg)