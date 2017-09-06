# 文件传输
* 远程复制文件`scp [参数] [原路径] [目标路径]`
    * 远程到本地
    
    `scp root@192.168.120.204:/opt/soft/nginx-0.5.38.tar.gz /opt/soft/`

    * 本地到远程

    `scp /opt/soft/ root@192.168.120.204:/opt/soft/nginx-0.5.38.tar.gz`
