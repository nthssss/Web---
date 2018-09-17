# Socket TCP客户端代码

客户端

* 通过connect\(\)调用、连接服务器，
* 连接成功后
  * 接收从服务器发来的数据，
  * 然后关闭连接、退出程序。

TCP的Python客户端代码如下：

```text
# -*- coding:utf-8 -*-
# 一点浩然气，千里快哉风。
import socket

HOST = '127.0.0.1'
PORT = 3434

sc = socket.socket(socket.AF_INET, socket.SOCK_STREAM)  # AF_INET指明使用IPV4地址，SOCK_STREAM指明TCP

sc.connect((HOST, PORT))
print("Connect %s:%d OK" % (HOST,PORT))
data = sc.recv(1024)
print("Received： ", data.decode())
sc.close()
```

TCP的Python客户端运行结果如下：

```text
Connect 127.0.0.1:3434 OK
Received：  Current time is 2018-05-22 12:08:56.872428
```

