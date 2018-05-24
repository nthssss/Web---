#C/S及B/S架构
---
C/S(Client/Server)：
- 当前大多数网络编程使用的架构模型。
- 通过它可以充分利用两端硬件环境的优势，将任务合理地分配到Client端和Server端来实现，降低了系统的通信开销。
- Client和Server常常分别处在相距很远的两台计算机上：
  - Client程序的任务是：
    - 将用户的要求提交给Server程序；
    - 再将Server程序返回的结果以特定形式显示给用户。
B/S（Browser/Server）：
- Web兴起后的一种网络结构模式。
- 使用Web浏览器作为客户端的应用软件，所以B/S可以看作C/S的一种特殊情况。
- 主要特点：
  - 便于部署、维护和升级：
    - 所有应用程序部署在服务器上，一般无须更新客户端软件（即浏览器）。
  - 跨平台、开放、对客户端要求低：
    - 每种操作系统都支持Web浏览器，基于B/S架构的系统只需开发一套客户端程序；
    - B/S架构的客户端程序部署在服务器端，由浏览器在访问时下载到客户端运行。
  - 对安全性的要求较高：
    - 由开放性而延伸多嗯嗯一个负面作用就是B/S架构对系统安全性的要求比C/S架构要高。
    - B/S架构的系统一般是建立在广域网上，面向未知用户，所以开发B/S系统时应该更加关注系统的**防攻击、数据加密、备份、防伪造**等能力。
    