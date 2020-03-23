### `HTTP`及`CORS`

---

- 状态码

  - 301： Moved Permanently 永久性转移
  - 302： Moved Temporarily 暂时性转移
  - 304： Not modified 未改变

  ---

  - 401： unauthorized	未授权（未登录）

  - 403： forbidden 隐藏
  - 404： not found 未找到
    - soft 404（软404），返回一状态码为200的页面，但内容是404页面的样子
    - IE浏览器对于小于512字节的404页面是不展示的 

  ---

  - 501： Not Implemented 请求方法不被服务器支持，请求无法被处理
  - 502： Internal Server Error 服务器内部错误

---

- 与缓存相关的头部信息

  - - `Last-Modified` （响应头） 第一次请求该资源时，在响应中携带该头部信息

    - `If-Modified-Since `（请求头） 后续继续请求（第二次及之后）该资源时，在请求中携带该头部信息

  - - `ETag` （响应头） 第一次请求该资源时，在响应中携带该头部信息
    - `If-None-Match` （请求头） 后续继续请求（第二次及之后）该资源时，在请求中携带该头部信息

  - - `Expiries`（响应头） 绝对时间

  - - `Age` （响应头）相对时间

  - - `Cache-Control` （既可以在响应头也可以在请求头） 具体使用方法看MDN

  - 前两组为协商缓存，后两个为强缓存，Cache-Control则两个都可以

---

- 常见的头部信息
  - 请求相关的首部：
    - `Host`：表示连接服务器所用的域名及其端口号（若有端口号的话）。可以用此特性来实现同一个服务器服务多个网站
    - `Referer`：表示连接服务器所在页面的完整地址。可以用来防盗链
    - `Origin`：表示连接服务器所在页面的域/源
    - `User-Agent`：浏览器标识，可以用`js`通过`navigator.userAgent`属性读取
  - 响应相关的首部：
    - `Date`：表示响应时服务器的时间
    - `Content-Type`：表示消息主体（请求/响应体）的类型
    - `Content-Length`：表示消息主体（请求/响应体）的长度，若使用了`Connection: keep-alive`（`TCP`连接复用，请求/响应中都可以带上）的话，必须带上该头部信息
    -   `Content-Security-Policy（CSP）`（内容安全策略）：告诉浏览器，页面中的`js`，甚至是其他资源能否被执行。
    - 

---

- 跳转
  - 前端跳转：返回的页面根据条件通过`js`来跳转 
  - `HTTP`跳转：用301/302状态码 + `Location`头来跳转
  - `HTTp`跳转一般是使用请求头中的`User-Agent`头
  - `HTTP`跳转对`XHR`是透明的

---

- `CORS`相关的头部信息
  - `Access-Control-Allow-Origin`
  - `Access-Control-Allow-Methods`
  - `Access-Control-Allow-Headers`
  - `Access-Control-Max-Age`

---

- 攻击：
  - `XSS （Cross Site Scripting）`：跨站点脚本攻击
  - `CSRF （Cross-site request forgery）`：跨站点请求伪造

