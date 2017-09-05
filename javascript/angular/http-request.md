> how

# 使用$http请求数据
```js
// $http.get(url, config);
$http.get(url, {
    params: {
        xx: 'xx'
    }
});
// $http.post(url, data, config);
$http.post(url, {
    arg: 'arg' 
}, {
    headers: {
        'Content-Type': 'application/json'
    }
});
```
