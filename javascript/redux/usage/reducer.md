# reducer注意事项
* state需要深拷贝
```js
let s = JSON.parse(JSON.stringify(state));
```