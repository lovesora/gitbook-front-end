# 轮询结果
```js
timer(0, 3000).take(5)
    .switchMap(() => {
        return http.postJSON('api/xxx');
    })
    .filter(data => data.code === 0)
    .first()
    .map(data => ({
        code: 200000,
        data
    }))
    .catch(data => {
        if (data.name && data.name === 'EmptyError') {
            return of({
                code: 100000,
                msg: '无数据！'
            });
        } else {
            return of({
                code: 100001,
                msg: '网络连接异常'
            });
        }
    });
```
