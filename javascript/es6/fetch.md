# Fetch
> How

### 请求json数据
```js
fetch('//httpbin.org/post', {
    method: 'POST',
    headers: {
        'Content-Type': 'application/json'
    },
    body: JSON.stringify({user: 'lx'})
})
.then(res => res.json())
.then(json => console.log(json.json))
.catch(e => {
    console.log(e);
});

//console {user: 'lx'}
```

# Resouces
* [**fetch API 简介**](http://bubkoo.com/2015/05/08/introduction-to-fetch/)
* [mdn fetch](https://developer.mozilla.org/zh-CN/docs/Web/API/GlobalFetch/fetch)
* [whatwg fetch](https://fetch.spec.whatwg.org/)