# throw捕获
```js
function fn(isTrue) {
    if (isTrue) {
        return 'true';
    } else {
        throw 'false';
    }
}

function callFn (fn) {
    console.log('start');
    fn(true);
    console.log('exe fn true');
    try {
        fn(false);
    } catch (e) {
        console.log('err: ', e);
    }
    fn(false);
    console.log('exe fn false');;
}

// start
// exe fn true
// err:  false
// Uncaught false
callFn(fn);
```