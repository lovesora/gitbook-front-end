# 需要学习的技术
* JS OOP
    * [ruanyifeng](http://javascript.ruanyifeng.com/oop/basic.html)

# 有时间可以阅读的文章
* [infoQ](http://www.infoq.com/cn/fp/?utm_source=infoq&utm_medium=header_graybar&utm_campaign=topic_clk)
    * [用GraphQL增强React](http://www.infoq.com/cn/articles/turbocharge-react-graphql)
    * [Go 构建日请求千亿级微服务的最佳实践](http://www.infoq.com/cn/presentations/best-practices-for-micro-service-on-the-go-construction-day)
    * [程立谈大规模SOA系统](http://www.infoq.com/cn/interviews/soa-chengli)
* swagger
    * [official site](https://swagger.io/)
    * [online](http://petstore.swagger.io/#/store/getInventory)
    * [知乎](https://zhuanlan.zhihu.com/p/21353795)
* chrome dev tools
    * [official doc](https://developers.google.com/web/tools/setup/setup-workflow?hl=zh-cn)
* [凹凸实验室 console](https://aotu.io/notes/2016/06/22/An-interesting-experience-on-console/index.html)

# 问题
* 对任务的评估不准确(是否可以枚举解决)
    * 时间
    * 角度
        * 健壮性
            * 网络
            * 异常操作(手动改disable)
            * 异常输入
            * 运算转换(json)
        * 扩展性
        * 复用性
        * 性能

* 目标性不强
    * 软件开发流程应该是可以枚举的
    * 并且可以按照优先级逐步逼近目标的
    * 进度监控
        * 燃尽图

* 规范(书面的文档)
    * git
        * [intro](http://www.jianshu.com/p/15b1e1127086)
    * 代码eslint(function (){}, tab)
    * 公共库更新
        * 更新方式，如何才需要更新
        * 命名、模块化(BEM)
    * 外部依赖（model用angular-ui还是bootstrap, table用ng-table还是ui-grid)
    * 接口定义的规范、更新
        * 能一次定好是最好的，接口改动看似只是加减一些字段，其实要改动很多代码，并且容易造成一些意料之外的错误
        * 字段命名
            * index_,index
            * sortindex,sortIndex
        * 字段类型(code string number)
        * RESTFul
* 前后端关于接口对接存在的问题
    1. 前端写假数据需要时间
        * 使用Mock解决假数据生成问题

    2. 接口变更，假数据的变更也需要花时间
        * 使用Rap自动生成假数据
        
    3. 接口变更频繁，文档没有修改
        * 接口变更的提出者需要及时修改接口文档

    4. 后端接口返回数据的格式发生变化的时候，前端不能及时响应
        * 吼
        * 微信

    5. 接口变更流程
        * 先交流->改文档->写mock规则->通知依赖接口的人->后端实现
    
    6. Rap的优势
        1. 通过nginx转发假数据太麻烦，通过rap更简洁，方便
        2. 假数据的生成问题（具体值）
        3. 解决了前端的部分接口测试问题

# 有时间可以整理的技术
1. angular boilerplate
2. ui-select
3. ng-table
4. descartes
5. dropdown
6. .form .form-group .input-group .input-group-btn
7. .font-aswome
8. swagger
9. codacy