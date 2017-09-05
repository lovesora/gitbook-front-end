> what

# yarn.lock 文件
保证每一次拉取同一个项目依赖时，使用的都是一样的模块版本
* [yarn.lock](https://yarnpkg.com/en/docs/configuration#toc-use-yarn-lock-to-pin-your-dependencies)
* [shrinkwrap.json](https://docs.npmjs.com/cli/shrinkwrap)

# install速度
* yarn安装依赖的速度绝大部分比npm快

# 更简洁的输出
* npm 的输出信息比较冗长。在执行 npm install <package> 的时候，命令行里会不断地打印出所有被安装上的依赖
* Yarn 默认情况下，结合了 emoji （Windows 上 emoji 不可见）直观且直接地打印出必要的信息，