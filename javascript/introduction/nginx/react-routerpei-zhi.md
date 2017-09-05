> How

# 配置React-Router
```bash
location ^~/react/ {
    alias /home/xin.liu/workspace/projectName/;
    index index.html;
    # /$1 是相对于root路径的
    # 注意没有last
    rewrite '.*/(.*?\.css.*)' /$1;
    # 加上last
    rewrite '.*/(.+?\.bundle\.js.*)' /$1 last;
    # 后面加上404 Nginx才会做内部转发
    try_files $uri index.html 404;
    #proxy_pass http://localhost:8880;
    #error_page 404 index.html;
}
```