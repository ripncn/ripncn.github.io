---
layout: post
title:  "使用Docker部署alist"
categories: docker
tags: docker alist
author: Ripncn
---

* content
{:toc}

# 拉取稳定版镜像
>docker run -d --restart=always -v /etc/alist:/opt/alist/data -p 5244:5244 --name="alist" xhofe/alist:latest

# 开发版镜像（不推荐）
* 不推荐，这有可能无法正常使用
>docker run -d --restart=always -v /etc/alist:/opt/alist/data -p 5244:5244 --name="alist" xhofe/alist:v2

# 指定版本镜像
具体见 <https://hub.docker.com/r/xhofe/alist>

# 初始密码请查看日志输出：
>docker logs alist
# 或者
>docker exec -it alist ./alist -password
