# 根据参数选择构建过程
1. 给SSH Server添加label

`构建后操作 -> send build artifacts over ssh -> ssh publishers -> ssh server -> name advanced`

2. 在`ssh publisher`中指定参数名

`send build artifacts over ssh -> ssh publishers -> advanced -> parameterized publishing -> parameter name`
