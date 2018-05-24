#基于HTTP的网站开发
---
##Web服务器：
handles(解析)HTTP

当Web服务器接收到一个HTTP请求（request）时：
- 根据配置的内容：
    - 返回一个静态的HTML页面；
    - 或者调用某些代码动态生成返回结果。

Web服务器把dynamic reponse(动态响应)的delegate（产生委托）给其他一些程序。
例如：
- Python代码；
- JSP（JavaServer Pages脚本）；
- Servlets；
- ASP（Active Server Pages）脚本等。

无论它们的目的如何，这些server-side（服务器端）程序通常会产生一个response(HTTP响应)可以让浏览器浏览。