---
layout: post
title:  "alist反向代理设置"
categories: docker
tags: docker alist
author: Ripncn
---

* content
{:toc}

## 程序默认监听5244端口
# nginx​

* 在网站的配置文件的server字段中加入

>location / {<br>
>   proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;<br>
>   proxy_set_header Host $http_host;<br>
>   proxy_set_header X-Real-IP $remote_addr;<br>
>   proxy_set_header Range $http_range;<br>
>   proxy_set_header If-Range $http_if_range;<br>
>   proxy_redirect off;<br>
>   proxy_pass http://127.0.0.1:5244;<br>
>   # 上传的最大文件尺寸<br>
>   client_max_body_size 20000m;<br>
>}<br>

### caution
* 如果你使用宝塔，请务必删除以下默认配置

    >location ~ ^/(.user.ini|.htaccess|.git|.svn|.project|LICENSE|README.md<br>
    >location ~ .*.(gif|jpg|jpeg|png|bmp|swf)$<br>
    >location ~ .*.(js|css)?$<br>

# Apache​

* 在VirtualHost字段下加入反代配置项ProxyPass，比如：

><VirtualHost *:80><br>
>   ServerName myapp.example.com<br>
>   ServerAdmin webmaster@example.com<br>
>   DocumentRoot /www/myapp/public<br>
><br>
>   AllowEncodedSlashes NoDecode<br>
>   ProxyPass "/" "http://127.0.0.1:5244/" nocanon<br>
></VirtualHost><br>

# Caddy​

* 在Caddyfile文件下加入反代配置项reverse_proxy，比如：

>:80 {<br>
>   reverse_proxy 127.0.0.1:5244<br>
>}
