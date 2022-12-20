---
layout: post
title:  "Typecho 无需插件实现友情链接功能"
categories: JavaScript
tags: Typecho Links
author: Ripncn
---

* content
{:toc}

# Typecho 无需插件实现友情链接功能

## 友情链接:
```html
<ul class="flinks">
<li>Ripncn's Blog</li>
<li>https://lovou.eu.org/</li>
<li>https://lovou.eu.org/favicon.ico</li>
<li>lovou.eu.org</li>

<li>枫铃网络</li>
<li>https://www.lovou.pw/</li>
<li>https://www.lovou.pw/favicon.ico</li>
<li>lovou.pw</li>

<li>枫铃博客</li>
<li>https://blog.lovou.pw/</li>
<li>https://blog.lovou.pw/favicon.ico</li>
<li>blog.lovou.pw</li>

<li>Free社区</li>
<li>http://free.lovou.pw/bbs</li>
<li>https://free.lovou.pw/bbs/favicon.ico</li>
<li>Free.lovou.pw/bbs</li>
</ul>
```





## 其他内容

又有一些链接
```html
<ul class="flinks">
<li>Lovou's Onedrive</li>
<li>https://one.mige.eu.org/</li>
<li>https://one.mige.eu.org/_next/image/?url=%2Ficons%2F128.png&w=32&q=75</li>
<li>mige.eu.org</li>

<li>枫铃网</li>
<li>https://blog.xongyi.com/</li>
<li>https://blog.xongyi.com/favicon.ico</li>
<li>blog.xongyi.com</li>

<li>Free Space</li>
<li>http://free.lovou.pw/</li>
<li>http://free.lovou.pw/favicon.ico</li>
<li>free.lovou.pw</li>

<li>在线网盘</li>
<li>https://pan.mige.eu.org/</li>
<li>https://pan.mige.eu.org/favicon.ico</li>
<li>mige.eu.org</li>
</ul>
```
## 结尾内容

这是文章结尾。
```
!!!
<script>document.querySelectorAll('ul.flinks').forEach(function(e){let a=e;if(a){let ns=a.querySelectorAll("li");let str='<div style="display:inline-block;">';let bgid=0;const bgs=["bg-white","bg-grey","bg-deepgrey","bg-blue","bg-purple","bg-green","bg-yellow","bg-red","bg-orange"];for(let i=0;i<ns.length;i+=4){str+=(`<div class="flink-item ${bgs[Math.floor(Math.random() * 9)]}"><div class="flink-title"><a href="${ns[i+1].innerText}"target="_blank"rel="external nofollow ugc">${ns[i].innerText}</a></div><div class="flink-link"><div class="flink-link-ico"style="background: url(${ns[i+2].innerText});background-size: 42px auto;"></div><div class="flink-link-text">${ns[i+3].innerText}</div></div></div>`)}str+=`</div>`;let n1=document.createElement("div");n1.innerHTML=str;a.parentNode.insertBefore(n1,a);a.style="display: none;"}else{console.log('No such id "flinks"')}});</script>
<style>.flink-item{width:300px;height:100px;position:relative;margin:10px;background-color:#fff;border-radius:3px;float:left}.flink-title{left:25px;top:25px;position:absolute}.flink-title a{font-size:17px;color:#f1f1f1;line-height:17px;word-break:break-all;text-decoration:none;outline:0}.flink-link{right:0;bottom:0;padding:0 15px 15px;position:absolute;text-align:center}.flink-link-text{font-size:12px;color:#f1f1f1}.flink-link-ico{display:inline-block;width:42px;height:42px;border-radius:50%}.bg-white{background-color:#fff!important}.bg-grey{background-color:#f7f7f7!important}.bg-deepgrey{background-color:rgba(0,0,0,.5)!important}.bg-blue{background-color:#6fa3ef!important}.bg-purple{background-color:#bc99c4!important}.bg-green{background-color:#46c47c!important}.bg-yellow{background-color:#f9bb3c!important}.bg-red{background-color:#e8583d!important}.bg-orange{background-color:#f68e5f!important}</style>
!!!
```
