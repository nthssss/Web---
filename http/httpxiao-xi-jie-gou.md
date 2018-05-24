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

### Request：

