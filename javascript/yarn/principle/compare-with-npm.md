# 什么是Yarn？
Yarn——Facebook、Google、Exponent 和 Tilde 联合推出的一个新的JS包管理工具，正如官方文档中写的，Yarn 是为了弥补 npm 的一些缺陷而出现的：
* npm 安装包（packages）的速度不够快，拉取的 packages 可能版本不同
* npm 允许在安装 packages 时执行代码，这就埋下了安全隐患

# yarn.lock 文件
保证每一次拉取同一个项目依赖时，使用的都是一样的模块版本
* [yarn.lock](https://yarnpkg.com/en/docs/configuration#toc-use-yarn-lock-to-pin-your-dependencies)
* [shrinkwrap.json](https://docs.npmjs.com/cli/shrinkwrap)

# install速度
* yarn安装依赖的速度绝大部分比npm快

# 更简洁的输出
* npm 的输出信息比较冗长。在执行 npm install <package> 的时候，命令行里会不断地打印出所有被安装上的依赖
* Yarn 默认情况下，结合了 emoji （Windows 上 emoji 不可见）直观且直接地打印出必要的信息，