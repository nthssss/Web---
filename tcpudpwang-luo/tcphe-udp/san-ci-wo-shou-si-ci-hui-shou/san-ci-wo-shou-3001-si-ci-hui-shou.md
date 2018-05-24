# 三次握手、四次挥手
---
## TCP连接正常建立和关闭对应的状态：

![](/assets/TCP中Socket正常连接和断开连接状态变迁.png)

TCP中的11种状态已经在此处体现了10种状态（还有一种CLOSING状态在同时关闭时出现）。

TCP正常连接、终止中的报文：

* SYN表示建立连接；
* FIN表示关闭连接；
* ACK表示响应。

## TCP正常建立连接-三次握手：

* 客户端发送SYN包到服务器，并进入SYN\_SENT状态，等待服务器确认。
* 服务器收到SYN包，反馈给客户端一个SYN+ACK包，此时服务器进入SYN\_RECV状态。
* 客户端收到服务器的SYN+ACK包，向服务器发送确认包ACK，客户端和服务器同时进入ESTABLISHED（TCP连接成功状态），完成三次握手。

## TCP正常关闭连接-四次挥手：

* 关闭请求方（比如客户端）向另一方发送（比如服务器）一个带有FIN附加标记的报文段；
* 服务器收到FIN报文段之后：
  * 不立即用FIN报文段回复客户端，
  * 先向客户端发送一个确认序号ACK，
  * 同时通知自己的相应的应用程序：对方要求关闭连接，使应用程序做相应的清理工作；
* 服务器的应用程序清理工作完成后，向客户端发送一个FIN报文段；
* 客户端收到这个FIN报文段后，向服务器发送一个ACK，表示连接彻底释放。
