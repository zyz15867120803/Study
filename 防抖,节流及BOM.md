### 防抖,节流及`BOM`

---

  ```javascript
// 防抖
function debounce(f, delay) {
    let timer = null;
    return function (...args) {
        clearTimeout(timer);
        timer = setTimeout(() => {
            f(...args);
        }, delay);
    };
}
  ```

```javascript
// 节流（此版本不仅考虑了时间还考虑到了最后一次事件的安排）
function throttle(f, delay) {
    let prev = Date.now();
    let timer = null;
    return function (...args) {
        let now = Date.now();
        clearTimeout(timer);
        if (now - prev >= delay) {
            f(...args);
            prev = now;
        } else {
             timer = setTimeout(() => {
                f(...args);
                prev = Date.now();
            }, delay);
        }
    };
}
```

---

##### `BOM`

- `screen`对象用于获取屏幕相关的信息
- `location`对象用于获取地址栏相关的信息
- - `host`属性：域名 —— 带端口号
  - `hostname`属性：域名 —— 不带端口号
  - `replace(url)`方法：掉用该方法能够将新的地址替换当前页面的地址，被替换的地址将不会被保存在历史记录中
  - 直接给`location`对象赋值，给`loacation.href`属性赋值，或调用`location.assign(url)`方法，这三种方式的效果相同，都是改变地址，使页面进行跳转
  - 更改`hash`属性不会让页面刷新(跳转)，但会触发`window.onhashchange`事件，可以在这个事件的`handler`里做出相应的操作(如刷新或请求`ajax`)(一般用来做前端路由)
- `history`对象用于获取当前页面的历史记录相关的信息 
- - `history.pushState(state, pageTitle, url)`方法更改`url`(`pathname`, `search string`和`hash`)不会刷新页面
  - 通过`window.onpopstage`事件，在浏览器前进后退至`pushState`方法打开的页面时，将页面修改回对应原来`url`的内容
- `navigator`对象用于获取浏览器相关的信息
- - `userAgent`属性：浏览器版本，内核等信息

---

- `getComputedStyle(node)`方法用于获取所有的样式
- `node.style`属性只能读取/设置行内样式

