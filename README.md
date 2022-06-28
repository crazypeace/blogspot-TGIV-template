# blogspot-TGIV-template
Telegram Instant View template for blogspot.com

```
#这个是TG IV的template的格式版本号，固定取值为 1.0 or 2.0 or 2.1
~version: "2.1" #使用最新的格式，固定为2.1

#判断是否是博文页面
#正则表达式
#/4个数字/2个数字/以.html结尾
?path: /\d{4}/\d{2}/.+\.html

########### Link Preview
#网站的名字 会出现在Link Preview中
site_name: //div[has-class("blog-name container")]

#博文的标题 会出现在Link Preview中
title: //h3[has-class("post-title entry-title")]

#简短介绍
#description: 

############ 
#作者名字，会表现在文章标题下
author: //span[has-class("fn")]

#点击作者名字后跳转的 URL
author_url: "https://github.com/crazypeace" 

#发布时间
#published_date:

#博文正文
body: //div[has-class("post-body entry-content float-container")]

#@remove: //iframe #Instant View 不支持 iframe，以是将其从模板中去掉 

# 将`<a>`和`<p>`标签下的`<img>`标签替换为`<figure>`，使子标签下的 <img> 正常显示
@replace_tag(<figure>): //a[.//img]
@replace_tag(<figure>): //p[.//img]

# 将blockquote换成pre
<pre>:  //blockquote
```
