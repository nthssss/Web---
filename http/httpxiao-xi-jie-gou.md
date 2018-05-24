#HTTP消息结构
---
<table>
        <tr>
            <th>Request消息结构</th>
            <td>
                <div>【请求方法】 【URL】【协议版本】</div>
                <div>【头字段1】：值1</div>
                <div>…</div>
                <div>【头字段n】：值n</div>
                <div>【空行】</div>
                <div>【请求体】</div>    
            </td>
        </tr>
        <tr>
            <th>Response消息结构</th>
            <td>
                <div>【协议版本】 【错误码】【错误字符串】</div>
                <div>【头字段1】:值1</div>
                <div>…</div>
                <div>【头字段N】:值N</div>
                <div>【空行】</div>
                <div>【响应体】</div>  
            </td>
        </tr>
    </table>

---
## 常用头字段：
HTTP中头字段以键值对的方式为服务器或客户端提供对方的信息。
本文中的方向指：
- Request方向：请求头，客户端发送给服务端；
- Reponse方向：响应头，服务端发送给客户端；
- Both方向：两个方向皆可。

**HTTP消息结构中没有Both这一说，Both仅在本文中指两个方向皆可。**
### Both：
|字段名|解释|可能的值|
|-|-|-|
|Etag|内容唯一标识。</br>客户端需要把服务器传来的Etag保留，在下次请求相同的URL时提交给服务器。</br>服务器用Etag值判断同一个URL的内容是否有变化，如有变化则发送更新的内容给客户端。|任何值|
|Via|列出从客户端到服务器或者相反方向的响应：</br>经过了哪些代理服务器；</br>用什么协议（和版本）发送请求。|-|

### Request：
|字段名|解释|可能的值|
|-|-|-|
|Accept|接受什么介质类型|type/sub-type</br>`*/*`表示任何类型</br>`*/type`表示该类型下的所有子类型|
|Accept-Charset|接收的字符集|ISO-8859-1|
|Accept-Encoding|接收的编码方法，通常指定</br>压缩方法、</br>是否支持压缩、</br>支持什么压缩方法。</br>|Gzip、deflate、UTF8|
|Accpet-Language|接收的语言|En、cn|
|Accpet-Ranges|服务器表明自己是否接受获取其某个实体的一部分（比如文件的一部分）的请求|bytes：表示接受</br>none：表示不接受。|
|Cahe-Control|对服务器的缓存控制|no-cahe：不要从缓存中去取，要求现在从Web服务器中去取|
|Connection|对服务器的连接控制|Close:告诉web服务器在完成本次请求的响应后，断开连接，不要等待本次连接的后续请求了</br>keep-alive：告诉Web服务器在完成本次请求的响应后，保持连接，等待本次连接的后续请求。|
|Host|客户端指定自己想访问的Web服务器的域名、IP地址和端口号。|IP:port|
|Proxy-Authenticate|提供自己在代理服务器中的身份信息|username:Password|
|range|需要获取对象的哪一部分内容|bytes=1024-  ：获取从第1024个字节到最后的内容|
|Referer|浏览器向Web服务器表明自己是从哪个URL获得当前请求中的URL的|http://www.baidu.com|
|User-Agent|指明浏览器的软件类型及版本|Mozila/x.x：Windows浏览器</br>Firefox/xx.x.x：Firefix浏览器|

## Reposne
|字段名|解释|可能的值|
|-|-|-|
|Age|实体从产生到现在经过了多长时间|-|
|Authorization|当客户端接收到来自Web服务器的WWW-Authenticate响应时，</br>该头部回应自己的身份验证消息给Web服务器|username:password|
|Cahe-Control|对客户端的缓存控制|Public：可以用缓存内容回应任何用户。</br>Private：只能用缓存内容回应先前请求该内容的那个用户。|
|Connection|对服务器的连接控制||
|Expired|||
|Location|||
|Proxy-Authenticate|||
|Server|||














