# 网络分层
---
Internet基于TCP/IP网络搭建。
TCP/IP将网络分为4层结构：应用层、传输层、网络层、接口层。



```
将数据从一个主机传输到另一个主机是一个复杂的过程，包括信息格式转换、分发、寻址、物理传输等，在这个过程中还要加入多种校验措施以保证传输的正确性。
为了使这个过程利于设计并且向开发者隐匿网络细节，计算机网络被纵向分割为不同的层，每一层表示不同的抽象程度和设计目的。
每一层的功能相互独立，这使得它们可以仅完成自己的任务，比如传输、编码等。
```
网络分层：
![](/assets/网络分层.png)
- 应用层（Application Layer）：
  - 为用户的进程直接提供服务，应用层负责发送及接收什么数据、如何解释数据、如何呈现数据、如何加密数据等问题，是网络应用程序开发者重点打交道的对象。
例如HTTPS定义了网络间数据加密及认证的标准方法、HTML定义了网页的解析方式等。
- 传输层（Transport Layer）：
  - 为两个主机的不同端口之间的通信提供服务。
  - 端口（Port）是一种在统一主机内不同通道之间进行寻址的方式。
  传输层的发送方与接收方在物理上无须相邻。
  - TCP/IP的传输层包括两种协议：TCP和UDP。
    - TCP提供可靠的有序传输；
    - UDP提供非可靠的传输。
- 网络层（Network Layer）：
  - 为两个主机之间提供通信服务。
  - 网络层定义了数据如何被封装为传送包，并且定义了不同主机之间的寻址方式。
  - 主要由IP组成。
- 接口层（Link Layer）：负责相邻物理设备之间的信息传输。
 - 接口层的工作非常多且复杂，它需要
   - 完成接口层的数据组装，
   - 加入必要的控制和校验数据，
   - 并且将二进制数据流（0/1）转换为物理链路上的标准电平（高电平、低电平）。
 - 针对不同的物理传输介质，接口层定义了多套标准，并且这些标准随着电子技术的进步一直发展。