# 工作技巧
* 工作效绩 = 单位时间产出 * 时间(12*8 == 8*12)
    * 重点在于产出二字，不要花费过多的时间在无关的事情上，记录下时间的走向

# 任务完成流程（PDCA）
* 一天之内的计划(明确任务内容（输入、输出）)
    * Why
    * What
    * Who
    * When
    * Where
    * Which
    * How
    * How much
* 划分任务细节
    * 检查项（需求）
        * 功能性需求
            * 界面
            * 输入
                * 键盘
                * 鼠标
            * 输出
                * 文本
                * 图片
                * 音视频
                * 列表
                * 表格
        * 非功能性需求
            * 性能
            * 用户体验
    * 依赖（需求、后端接口、UI）
    * modules
        * tasks
* 给出细节时间消耗
    * per task
* 按照优先级给出细节任务计划
    * order
* 给出全局时间消耗
    * per module
    * per goal
* 把控进度
    * ph
    * pd
    * pw
    * pm
    * pq
    * py
* 输出备忘
    * day blog（碎片化知识）
    * github（代码）
    * gitbook（体系化知识，细节）
    * baidu脑图（思维导图（宏观关联，而非细节））
    * 掘金、简书、segmentfault、开发者头条（技术博客，有技术含量的文章，纵向深入）
* 计划评估
    * 结果与期望比例


# 规范
* API接口
    * REST
    * swagger
    * rap
    * 变更
        1. 交流讨论是否可以变更
            * why
            * priority
        2. 修改文档
            * rap
            * md
        3. 写mock规则
        4. 通知依赖接口的人
        5. 接口实现
* Git
    * workflow
* 代码风格eslint
    * js
    * html
    * css
* code review
    * codacy
* 开发流程
    1. Sketch原型+标注
    2. Interface定义
    3. Mock数据
    4. Fetch
    5. View
    6. DTS
    7. Controller
    8. UI
    9. UE
    10. Test
* 进度监控
    * 燃尽图
* DB
    * 脚本
    * 变更
* 环境配置
    * Nginx配置
        * 路由
        * 反向代理
            * 开发
            * 测试
            * 本地
            * rap
            * service
* 持续集成（频繁地（一天多次）将代码集成到主干）
    > 快速发现错误

    > 防止分支大幅偏离主干

    * Jenkins