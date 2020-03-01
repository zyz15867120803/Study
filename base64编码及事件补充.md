### `base64`编码及事件补充

---

- `btoa`函数用于将元数据编码为`base64`编码的数据
- `atob`函数用于将`base64`编码的数据解码为元数据
- `node`中用`Buffer.from('xxxx', 'base64').toString()`方法将编码后的数据转换为字符串（`xxxx`代表编码后的数据）
- `Data URI`：`data: [<MIME type>][;charset=<charset>][;base64],<encoded data>`
- - 整体可分为3部分，声明，参数和数据
  - 声明：`data:`是`URI`的协议头，表明其资源是一个`data URI`
  - 参数：`MIME type`表示数据的呈现格式，即指定嵌入数据的`MIME`，对于`PNG`图片，其格式为`image/png`，默认为`text/plain`。`charset`（字符集）大多被忽略，默认为`charset=US-ASCII`，若指定的数据格式为图片时，字符集将不再使用。`base64`表示其数据的编码方式，不一定要用`base64`编码
  - 数据：`encoded data`为实际编码的数据

---

- `online`事件：机器由掉线状态转为上线状态时触发
- `offline`事件：机器由上线状态转为掉线状态时触发
- `error`事件：严格来说不是一个事件，因为不只接一个事件对象，而是接五个参数，分别是：错误消息，出错的文件路径，行号，列号和错误对象。（大多用于错误收集和上报）
- - 当出错的文件是来自其他域的时候，接收的参数几乎是没有意义的
  - 当此事件用`addEventListener`注册时，只接一个参数
- 移动端`click`事件300ms延迟问题

