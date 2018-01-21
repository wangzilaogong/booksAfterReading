# 	《图解HTTP》— HTTP报文信息	

##HTTP报文

​	HTTP报文结构主要是报文首部、CR+LF、报文主体。如图所示，清楚明了。

![](http://oydcisax6.bkt.clouddn.com/20171102143929_T52J7a_Screenshot.jpeg)

​	实例 ：请求和响应报文

![](http://oydcisax6.bkt.clouddn.com/20171102144540_14jtv9_Screenshot.jpeg)

## 编码提升传输速率

### 编码速率

​	http传输信息分2种，原貌和编码传输。编码传输可以进行处理大量访问请求，但是会消耗很多的CPU资源。

### 报文主体和实体主体

* 报文  8位组字节流组成，HTTP通信

* 实体   有效荷载数据，首部实体+实体主体

  通常HTTP报文主体等于实体主体，只有在传输过程中进行编码操作时，实体内容发生变化，才导致喝报文主体产生差异。

### 压缩传输的内容编码

​	内容编码由客户端进行解码

![](http://oydcisax6.bkt.clouddn.com/20171102151739_1ixtkE_Screenshot.jpeg)

### 分块传输编码

![](http://oydcisax6.bkt.clouddn.com/20171102151921_9sXFIY_Screenshot.jpeg)

## 发送多部分对象合集

​	其实就是我们常说的MIME类型，利用MIME来标记数据类型，MIME扩张了一种对象合集方法。

* multipart/form-data 正好最近刚刚写了一个上传表单的文件![](http://oydcisax6.bkt.clouddn.com/20171102153401_zEgKt9_Screenshot.jpeg)

* multipart/byteranges  状态码206  响应报文包含多个范围的内容使用。

  使用boundary字符串来划分多部分对象集合指明的各类实体。

## 获取部分内容的范围请求

​	对于资源的部门请求，意思就是10000字节的先拿一半或者指定字节部分。

![](http://oydcisax6.bkt.clouddn.com/20171102154412_762Sz0_Screenshot.jpeg)

## 内容协商

​	该机制值客户端和服务器对于响应资源内容进行交涉，然后提供合适的资源。请求报文有字段规定。

* 服务器驱动  以请求的首字母进行参考。服务器处理。

* 客户端驱动  客户端（浏览器）手动选择，js脚本进行选择。os类型、浏览器类型，pc或者手机页面。

* 透明协商  ，双方结合的方式。

  ​