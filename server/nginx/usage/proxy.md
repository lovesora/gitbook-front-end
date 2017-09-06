# 配置Nginx反向代理

```bash
# nginx/nginx.conf
http {
    include servers/*.conf;
}
```

```bash
# nginx/servers/xxx.conf
server {
    location /api {
        # 反向代理
        proxy_pass http://domain:port/path;
        include proxy.conf;
    }
}
```

```bash
# nginx/proxy.conf
proxy_redirect          off;
proxy_set_header        Host $host;
proxy_set_header        X-Real-IP $remote_addr;
client_max_body_size    10m;
client_body_buffer_size 128k;
proxy_connect_timeout   300;
proxy_send_timeout      300;
proxy_read_timeout      300;
proxy_buffer_size       4k;
proxy_buffers           4 32k;
proxy_busy_buffers_size 64k;
proxy_temp_file_write_size 64k;
```
