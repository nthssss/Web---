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
|Via|列出从客户端到服务器或者相反方向的响应：</br>经过了哪些代理服务器；</br>用什么协议（和版本）发送请求。||

### Request：
|字段名|解释|可能的值|
|-|-|-|
||||
|Accept|接受什么介质类型|type/sub-type</br>`*/*`表示任何类型</br>*/type表示该类型下的所有子类型|
|Accept-Charset|||
|Accept-Encoding|||
|Accpet-Language|||
|Accpet-Ranges|||
|Cahe-Control|||
|Connection|||
|Host|||
|Proxy-Authenticate|||
|range|||
|Referer|||
|User-Agent|||

## Reposne
|字段名|解释|可能的值|
|-|-|-|
||||

