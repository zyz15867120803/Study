### 表单`DOM`

---

-  文本框的`change`事件只会在光标移出输入框后才触发
- 元素的内容通过`js`改变的话，是不会触发`change`事件的
- 如果想在输入过程中就探测其改变，则可使用`keydown`,`keyup`,`keypress`或`input`事件
- 输入法事件`compositionstart`和`compositionend`
- `selectionStart`和`selectionEnd`属性用来读取和设置文本框中鼠标的选区位置
-  `storage`事件：当前页面修改`localStorage`时，同一站点下的其他页面（不包含当前页面）会收到`storage`事件
- `URL.createObjectURL(File/Blob)`