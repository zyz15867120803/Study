### `Queue`队列的实现

---

```javascript
 class Queue {
     constructor() {
         this.tasks = []; // 保存队列中待执行的函数
         this.hasRunning = false; // 是否有函数正在执行
     }
     add(f) {
         let self = this;
         // 若没有正在执行的函数，则直接执行该函数，否则添加到待执行函数队列的尾部
         if (!this.hasRunning) {
             this.hasRunning = true;
             f(function next() {
                 // 若队列中有待执行的函数，则取出第一个执行
                 if (self.tasks.length > 0) {
                     let nextTask = self.tasks.shift();
                     nextTask(next);
                 } else {
                     self.hasRunning = false;
                 }
             })
         } else {
             this.tasks.push(f);
         }
         return this;
     }
 }
```