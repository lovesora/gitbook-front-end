# 注册服务
```js
app.factory('serviceName', function ($http, $q) {
    let defer = $q.defer();
    let service = {};
    service.fn = function(){
        setTimeout(() => {
            defer.resolve('success');;
        }, 0);
        return defer;
    };
    return service;
}
```

```js
app.controller('controllerName', function(serviceName){
    serviceName.fn().promise.then(data => {
        console.log(data);// success
    });
});
```
