### 鼠标键盘事件及this

---

* `window`对象自带`length`属性，该属性返回当前窗口中包含的框架数量(框架包含`frame`和`iframe`两种元素)

* 数组的高级函数都可以接2个参数，第二个参数用来绑定回调函数中的`this`

---

* `keypress`事件只对产生字符输入的键生效

* `click`事件会在同时包含鼠标按下和鼠标松手的最能层元素上触发

* `event` 事件对象的鼠标按键属性

* - `which`属性表示哪一个鼠标按键被按下，0表示无，1表示左键，2表示中键，3表示右键，但无法表示组合鼠标键，该属性总是只展示最先按下去的键

  - `buttons`属性表示哪些鼠标按键被按下，它的二进制形式的最低位表示左键，第二位表示右键，第三位表示中间，例如按下左键`buttons`的值为1(二进制形式为`0b001`)，同时按下中键和右键就会得到6，以此类推

  - ```javascript
    const MOUSE_LEFT = 1; // 二进制形式为0b001
    const MOUSE_RIGHT = 2; // 0b010
    const MOUSE_MIDDLE = 4 // 0b100
    
    if (event.buttons === (MOUSE_LEFT | MOUSE_MIDDLE)) {
    } // 判断是否同时按下鼠标左键和中键
    ```

---

- `mouseover`和`mouseout`事件冒泡，且当鼠标从父元素移到子元素时，也会触发父元素的`mouseout`事件
- `mouseenter`和`mouseleave`事件可以用来代替上面两个事件，同时`mouseenter`和`mouseleave`事件不冒泡，能够避免不必要的问题
- `focus`和`blur`事件不冒泡，`focusin`和`focusout`事件冒泡

---

- `scroll`事件无法阻止默认行为，其原因是滚动发生在事件处理程序(函数)之前，要想禁止滚动，可以阻止`mousewheel`/`DOMMouseScroll`事件的默认行为
- `addEventListener`方法的第三个参数可以是一个选项对象，该对象的属性值均为`boolean`类型
- - `capture`,表示是否在捕获阶段触发
  - `once`，若为`true`，表示事件处理程序在添加后最多只能调用一次，被调用后自动移除
  - `passive`，若为`true`表示事件处理程序永远不会调用`preventDefault`方法，若在其中调用了该方法，浏览器会将其忽略，并抛出警告



