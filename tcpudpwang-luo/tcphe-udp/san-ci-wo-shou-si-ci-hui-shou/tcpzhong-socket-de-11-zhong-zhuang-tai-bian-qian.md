#TCP中Socket的11种状态变迁
---
##TCP中Socket的11种状态变迁（了解）
![](/assets/TCP中Socket状态变迁.png)

## 2MSL

MSL

Maximum Segment Lifetime 报文最大生存时间：

* 是任何报文在网络上存在的最长时间，超过这个时间报文将被丢弃。
* tcp报文（segment）是ip数据报（datagram）的数据部分，而ip头中有一个TTL（time to live 生存时间）域：
  * 生存时间是由源主机设置初始值但不是存的具体时间，而是存储了一个ip数据报可以经过的最大路由数，
    * 每经过一个处理他的路由器此值就减1，
    * 当此值为0则数据报将被丢弃，同时发送ICMP报文通知源主机。
* 规定MSL为2分钟，实际应用中常用的是30秒，1分钟和2分钟等。

2MSL即两倍的MSL，TCP的`TIME_WAIT`状态也称为2MSL等待状态：

- 当TCP的一端发起主动关闭，在发出最后一个ACK包后，即第三次挥手完成后发送了第四次挥手的ACK包后就进入了`TIME_WAIT`状态；
- 必须在此状态上停留两倍的MSL时间，这样可以让TCP再次发送最后的ACK以防这个ACK丢失（另一端超时并重发最后的FIN）。

TTL与MSL是有关系的但不是简单的相等的关系，MSL要大于等于TTL。

