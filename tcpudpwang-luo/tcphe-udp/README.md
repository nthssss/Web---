# TCP和UDP

* C/S及B/S架构
* 三次握手四次挥手

传输层是TCP/IP网络中承上启下的关键一层：

* 向上对应用层提供通信服务；
* 向下将应用信息封装为网络信息。

  传输层：

* 连接主机之间的进程，同一主机中不同进程的网络通信通过端口\(port\)进行区分；
* 所以传输层为主机提供的是端口到端口的服务。

| 传输层协议 | 介绍 | 特点 |
| :--- | :--- | :--- |
| TCP | 面向连接、可靠、基于字节流 | 有序性：为每个数据包编排序号，使接收端能够判断先后到达的次序混乱的数据包的原本顺序； 正确性：TCP用一个checksum函数来检验数据是否有错误，在发送和接收时都要计算、校验，使得接收端能够判断数据是否在传输过程中破坏； 可靠性：发送端采用超时重传并有确认机制识别错误或丢失数据，进行重发； 可控性：接收端和发送端的网络质量通常不同，TCP采用滑动窗口协议和拥塞控制算法使数据的发送速度达到合理值。 |
| UDP | 无连接 | 数据可以随时发送、接收，没有建立、断开连接的过程，因此主机不需要维护复杂的连接状态； UDP不保证数据的可靠传输，仅仅尽最大可能进行发送； 没有拥塞机制控制算法控制收发速率，程序需在应用层自行控制。 发送方的UDP对应用程序交付的报文，在添加首部后就向下交付给IP层。既不拆分，也不合并。因此，应用程序需要选择合适的报文大小。 |

