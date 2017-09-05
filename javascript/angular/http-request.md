> How

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

# 封装request
```js
// ajax.fetch.js

define(['angular', 'app', 'errorConstant', 'responseConstant'], function(angular, app, errMsg) {
    
    app.factory('ajax', function($http, $q, RESPONSE_COMMON_ERROR, RESPONSE_TYPE) {

        let service = {};

        /**
         * config: {
         *  method: ['GET', 'POST', 'PUT', 'DELETE'],
         *  url: '/api',
         *  data: {}
         * }
         */
        service.request = (config, restUrlParams = {}) => {
            let _config = Object.assign({}, config, {
                headers: {
                    'Content-Type': 'application/json;charset=utf-8'
                }
            });

            angular.forEach(restUrlParams, function(paramValue, paramKey) {
                _config.url.replace(':' + paramKey, paramValue);
            });
            
            let defer = $q.defer();
            $http(_config).then(res => {
                let data = res.data;
                let status = res.status;
                if (200 <= status && status < 300) {
                    defer.resolve(data);
                } else {
                    defer.reject(res);
                }
            }, res => {
                let status = res.status;
                if (400 <= status && status < 500) {
                    defer.reject(status + ': ' + errMsg.ERROR_NETWORK_CLIENT);
                } else if (500 <= status && status < 600) {
                    defer.reject(status + ': ' + errMsg.ERROR_NETWORK_SERVER);
                } else {
                    defer.reject(status + ': ' + errMsg.ERROR_UNKNOWN);
                }
            });
            return defer.promise.then(data => {
                if (angular.isObject(data)) {
                    if (data.code === RESPONSE_TYPE.SUCCESS) {
                        return data.data;
                    } else {
                        throw data.message || (data.error && data.error.message) || RESPONSE_COMMON_ERROR.WRONG_RESPONSE;
                    }
                } else {
                    throw RESPONSE_COMMON_ERROR.UNKNOWN;
                }
            });
        };

        return service;
    });
});
```

```js
// error.constant.js
define([], function() {
    return {
        'ERROR_SERVER_INTERNAL': '服务器返回了一个错误信息',
        'ERROR_NETWORK_CLIENT': '客户端请求错误',
        'ERROR_NETWORK_SERVER': '服务器内部错误',
        'ERROR_UNKNOWN': '未知错误',
        'ERROR_NETWORK_ERROR': '网络出现错误'
    };
});
```

```js
// response.constant.js
define(['angular', 'app'], function(angular, app) {
    app.constant('RESPONSE_COMMON_ERROR', {
        'WRONG_RESPONSE': '服务器返回了错误的信息',
        'UNKNOWN': '未知错误'
    });
    
    app.constant('RESPONSE_TYPE', {
        'SUCCESS': 0
    });
});
```

```js
// usage
service.getList = data => {
    let config = {
        url: '',
        method: 'GET'
    };
    config.params = data;
    return ajax.request(config);
};

service.postData = data => {
    let config = {
        url: '',
        method: 'POST'
    }
    config.data = data;
    return ajax.request(config);
};
```