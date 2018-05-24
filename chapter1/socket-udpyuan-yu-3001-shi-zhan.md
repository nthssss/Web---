# Socket UDP原语

---

* UDP相对于TCP在传输层提供更少的控制，没有建立连接、断开连接等概念，所以基于UDP的Socket通信过程也比TCP稍微简单。
* 在UDP中可以直接通过指定`IP：Port`进行数据收发。
* UDP Socket可以复用TCP中的socket\(\)和bind\(\)原语，除此之外，UDP属于自己的Socket原语如下。

---

以下为**仅在UDP中使用**的原语：

* recvfrom\(\)：从绑定的地址接收数据。
* sendto\(\)：向指定的地址发送数据，在调用的参数中应该传入通信对端的地址和端口。

---

示例中：

* 服务端：
  * 通过socket\(\)和bind\(\)调用绑定了本地所有地址的3434端口；
  * 通过socket\(\)中的SOCK\_DGRAM指定Socket使用UDP；
  * 在一个循环中不断地接收数据并打印。
* 客户端：
  * 直接调用sendto\(\)向指定的地址发送数据。

---

UDP的Python服务端代码如下：

```
# -*- coding:utf-8 -*-
# 一点浩然气，千里快哉风。
import socket

HOST = '0.0.0.0'
PORT = 3434

ss = socket.socket(socket.AF_INET, socket.SOCK_DGRAM)  # AF_INET指明使用IPV4地址，SOCK_DGRAM指明UDP
ss.bind((HOST, PORT))  # 绑定IP与端口

while True:
    data, addr = ss.recvfrom(1024)  # 本次接收最大数据长度为1024
    print("Receiced： %s from %s" % (data.decode(), str(addr)))

ss.close()
```

UDP的Python客户端代码如下：

```
# -*- coding:utf-8 -*-
# 一点浩然气，千里快哉风。
import socket

HOST = '127.0.0.1'
PORT = 3434

sc = socket.socket(socket.AF_INET, socket.SOCK_DGRAM)  # AF_INET指明使用IPV4地址，SOCK_DGRAM指明UDP


data = "Hello UDP!"
sc.sendto(data.encode(), (HOST,PORT))
print("Sent: %s to %s:%d" % (data, HOST, PORT))

sc.close()
```

---

UDP的Python服务端运行结果如下：  
**客户端端口52824由客户端程序在调用sendto\(\)时自动生成。**

```
Receiced： Hello UDP! from ('127.0.0.1', 52824)
```

UDP的Python客户端运行结果如下：

```
Sent: Hello UDP! to 127.0.0.1:3434
```



