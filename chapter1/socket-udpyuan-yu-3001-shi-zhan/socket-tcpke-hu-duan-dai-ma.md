# Socket TCP客户端代码
---


```
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

