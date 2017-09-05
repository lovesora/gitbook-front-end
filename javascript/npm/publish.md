> How

# 如何搭建npm库
1. [npm官网](https://www.npmjs.com/)注册账号
2. 本地终端运行`npm adduser`
3. `package.json`

    ```js
    {
        "name": "projectName", // package的名称
        "author": "liuxin <475212506@qq.com>", // 作者的相关信息
        "version": "0.0.1", // 版本号(semantic version)
        "main": "index" // 入口文件，当在其他文件中require('projectName')时，将会加载index.js
    }
    ```

4. 发布`npm publish`
5. 更新版本`npm version patch && npm publish`


# Resouces
* [搭建前端私有npm杂记](http://www.cnblogs.com/lvdabao/p/frontend-private-npm.html)