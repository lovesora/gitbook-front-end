# 查找
* find
```bash
# 查找当前文件夹下扩展名为.map的所有文件并删除
find ./ -name '*.map' | xargs rm -rf

# 查找当前文件夹下包含name字符串的文件
# -r 递归 -l只显示文件名 -E正则表达式
grep -r -l -E 'proxy' ./
```