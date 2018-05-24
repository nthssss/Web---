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
### Request：

