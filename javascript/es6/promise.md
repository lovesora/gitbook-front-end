# Promise

> What

### 链式调用
```js
/**
 * 1. throw进入错误信息捕获
 * 2. return进入正确信息捕获
 * 
 * success -> return -> success
 * success -> throw  -> failure
 * failure -> return -> success
 * failure -> throw  -> failure
 */
new Promise(res => {
    setTimeout(() => {
        let r = 'res';
        console.log(r);//res
        res(r);
    }, 0);
}).then(r => {
    r = r + ' -> then';
    console.log(r);//res -> then
    return r;
}).then(r => {
    r = r + ' -> then';
    console.log(r);//res -> then -> then
    // throw 不会进入下一个then的第一个回调
    throw r;
}).then(r => {
    r = r + ' -> then';
    console.log(r);//不会执行
    return r;
}).then(()=>{}, rej => {
    rej = rej + ' -> rej';
    console.log(rej);//res -> then -> then -> rej
    // return 会进入下一个then的第一个回调
    return rej;
}).then(r => {
    r = r + ' -> then';
    console.log(r);//res -> then -> then -> rej -> then
    return r;
}, rej => {
    rej = rej + ' -> rej';
    console.log(rej);//不会执行
    return r;
}).catch(e => {
    e = e + ' -> catch';
    console.log(e);//不会执行
    return e;
}).then(r => {
    r = r + ' -> then';
    console.log(r);//res -> then -> then -> rej -> then -> then
    throw r;
}).catch(e => {
    e = e + ' -> catch';
    console.log(e);//res -> then -> then -> rej -> then -> then -> catch
    return e;
})
```

# Resouces
* [MDN Promise](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Promise)
* [传统 Ajax 已死，Fetch 永生](https://github.com/camsong/blog/issues/2)
* [Promises/A+](https://promisesaplus.com/)