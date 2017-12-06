# vim
## 进入visual模式
* v                 进入visual模式
* shift + v         进入行visual模式
* ctrl + v          进入块visual模式
* :m +/- number     向下／上移动number行

## custom map
* ctrl + j          向下移动
* ctrl + k          向上移动

# NERDTree
## 切换工作台和目录
* t, T              新建tab，大写代表静默
* ctrl + w + h      光标 focus 左侧树形目录
* ctrl + w + l      光标 focus 右侧文件显示窗口
* ctrl + w + w      光标自动在左右侧窗口切换
* ctrl + w + r      移动当前窗口的布局位置

## 分屏
* s, gs             水平分屏, g代表静默
* i, gi             垂直分屏, g代表静默

## 控制
* P                 跳到根结点
* p                 跳到父结点
* K                 跳到当前目录下同级的第一个结点
* J                 跳到当前目录下同级的最后一个结点
* k                 跳到当前目录下同级的前一个结点
* j                 跳到当前目录下同级的后一个结点
* cd                设置根目录pwd为当前目录
* !                 执行当前文件
* I                 切换是否显示隐藏文件
* f                 切换是否使用文件过滤器
* F                 切换是否显示文件
* B                 切换是否显示书签
* o                 打开菜单
* r                 刷新当前选中目录
* R                 刷新根目录


# Nerdcommenter
* [number]<leader>cc        注释
* [number]<leader>cu        取消注释
* [number]<leader>c<space>  toggle注释
* [number]<leader>cI        在行末尾添加注释
* [number]<leader>ca        切换注释


# CtrlP
* ctrl + p                  打开文件查找


# vim-multiple-cursors
* ctrl + n                  多行筛选下一个
* ctrl + m                  回退上一个筛选
* ctrl + x                  跳过该次筛选

# vim-sort-motion
* gs                        执行排序


# vim-argwrap
* <leader> + a              将一行参数转换为多行参数
