# Fetch
> How

### 请求json数据
```js
fetch(api.url, {
    method: api.type
})
.then(response => response.json())
.then(json => {
    console.log(json);
})
.catch(e => {
    console.log(e);
});
```


# Resouces
* [mdn fetch](https://developer.mozilla.org/zh-CN/docs/Web/API/GlobalFetch/fetch)
* [whatwg fetch](https://fetch.spec.whatwg.org/)