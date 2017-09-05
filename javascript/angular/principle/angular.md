# angular项目目录结构

```
|-src                                       // 源文件目录
    |-assets                                // 资源文件所在目录
        |-png                               // png图片文件夹
            |-xxx.png                       // 具体png图片文件
    |-directives                            // 指令所在文件夹
        |-directiveName                     // 指令模块
            |-directiveName.directive.js    // 具体指令js
            |-directiveName.directive.css   // 具体指令css
    |-scripts                               // 公共js代码
        |-main.js                           // require.js入口文件（定义文件依赖）
        |-app.js                            // 定义app路由、拦截器等
    |-services                              // 服务目录
        |-dts                               // 数据转换服务（将原始数据转换成与View层相耦合的数据，Controller中不再做数据转换）
            |-moduleName                    // 功能模块目录（如：订单模块、喂食器管理模块等）
                |-xxx.dts.js                // dts文件
        |-fetch                             // 获取后端接口数据服务
            |-moduleName                    // 模块名
                |-xxx.fetch.js              // 获取后端提供的接口数据
        |-common                            // 公共库
            |-ajax.service.js               // 封装请求码错误判断
        |-constant                          // 常量目录
            |-api.constant.js               // 后端REST API url管理
            |-error.constant.js             // 错误常量
    |-styles                                // 全局css样式所在文件夹
        |-xxx.css                           // 全局css样式
    |-views                                 // 视图层
        |-moduleName                        // 模块名
            |-xxx.html                      // html
            |-xxx.css                       // 样式文件
            |-xxx.controller.js             // 控制器
```