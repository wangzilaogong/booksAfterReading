# 《图解HTTP》—Web服务器

## 一台服务器上多站点

​	物理层面使用一台服务器，可以使用虚拟主机的功能，模拟多台服务器。网址输入之后通过dns服务映射到ip地址。如果一台服务器上部署了多个网站。那么他们的访问 IP也是一样的，那么我们dns出来之后到底是访问的哪个网站呢？因此，HTTP发请求的时候必须在Host首部完整指定主机名或域名URI。

## 代理、网关、隧道

​	标题内容都是HTTP在通信的时候除了客户端和服务器之外的用于通信数据转发的应用程序。

​	**代理**：转发功能。接收由客户端发出的请求并且转发给服务器，同时接收服务器的响应也同时转发给客户端。

​	HTTP通信过程中，每次通过代理服务器的时候都会附加Via首部字段标记出主机信息。

​	为什么要使用代理呢？利用缓存技术减少对于网络带宽的流量，组织内部对于特定的网站访问控制，以获取访问日志为主要目的（不太明白这句话）。代理的使用方法2种，一种是<u>是否使用缓存</u>，第二种<u>是否修改报文</u>。

​	*缓存代理* 预先将资源的副本保存在代理服务器上，那么就可以再次请求的时候就不需要从源服务器上获取了，直接从代理上拿之前缓存的资源。

​	*透明代理* 不对报文加工的。

​	**网关**  也是转发服务器器通信数据的服务器，说到底还是服务器啊。

![](http://oydcisax6.bkt.clouddn.com/20171104110349_iu9AUr_Screenshot.jpeg)

​	利用网关可以将HTTP请求转换为其他协议通信。网关可以使通信线路上的服务器提供非HTTP协议。网关可以连接数据库，使用sql语句查询数据。

​	**隧道**  使用SSL 等加密手段进行通信。

## 缓存服务器

​	利用缓存可以避免多次从源服务器转发资源，客户端就可以从近的缓存服务器上获取资源。服务器也可以减少对于相同请求次数。

![](http://oydcisax6.bkt.clouddn.com/20171104141803_lIsIba_Screenshot.jpeg)

## 客户端缓存

​	客户端缓存就是浏览器缓存。

![](http://oydcisax6.bkt.clouddn.com/20171104144007_5Jt5WM_Screenshot.jpeg)



