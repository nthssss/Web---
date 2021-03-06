# Socket TCP原语、实战

以下为**仅在TCP中使用**的原语：

## 在TCP服务端、客户端都可使用的Socket原语：

* send\(\)：发送数据。
  * 向对方发送数据；
  * send\(\)参数中传入要发送的数据，通过send\(\)的返回值判断数据是否发送成功。
* recv\(\)：接收数据。
  * 如果Socket中没有数据可读取：
    * 默认情况下recv\(\)调用会被阻塞直到有消息到达；
    * 开发者可以将Socket设置为非阻塞模式，使Socket以失败形式返回。

## 仅在TCP服务端使用的Socket原语：

* listen\(\)：服务端监听。
  * 告诉操作系统开始监听之前绑定的IP地址和端口，可以在传入参数中指定**允许排队的最大连接数量**。
* accept\(\)：服务端接收连接。
  * **从监听到的连接中取出一个，并将其包装成一个新的Socket对象。**
  * **这个新的Socket对象可被用于和相应的客户端进行通信。**
  * 完成accept\(\)标志着Socket已经完成了TCP连接的三次握手。
  * 如果当前没有客户端连接请求，则accept\(\)调用会阻塞等待。

## 仅在TCP客户端使用的Socket原语：

* connect\(\)：客户端连接服务器。
  * 参数中指定服务器的**地址和端口（元组）**。
  * 调用connect\(\)有两种结果：
    * 与服务器完成TCP三次握手并建立连接；
    * 连接失败。

