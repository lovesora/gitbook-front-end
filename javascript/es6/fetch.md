# 使用fetch请求json数据
```js
fetch(api, {
    method: url.awards.list.type
})
.then(response => response.json())
.then(json => {
    if (0 == json.code) {
        this.props.getAwardsListData(json.data);
    } else {
        console.log(json);
    }
})
.catch(e => {
    console.log(e);
});
```

# Resouces
* [mdn fetch](https://developer.mozilla.org/zh-CN/docs/Web/API/GlobalFetch/fetch)
* [whatwg fetch](https://fetch.spec.whatwg.org/)