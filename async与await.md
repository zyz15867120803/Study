### `async`与`await`

---

- 实现原理

```javascript
function run(generatorFunc) {
    return new Promise((resolve, reject) => {
        let iterator = generatorFunc();
        let generated = null;
        try {
            generated = iterator.next();
        } catch(e) {
            reject(e);
        }

        step();

        function step() {
            if(!generated.done) {
                generated.value.then(val => {
                    try {
                        generated = iterator.next(val);
                    } catch(e) {
                        reject(e);
                    }
                    step();
                }, reason => {
                    try {
                        generated = iterator.throw(reason);
                    } catch(e) {
                        reject(e);
                    }
                    step();
                })
            } else {
                Promise.resolve(generated.value).then(resolve, reject);
            }
        }
    })
}
```

---

- `await`只能放在`async`的函数里面