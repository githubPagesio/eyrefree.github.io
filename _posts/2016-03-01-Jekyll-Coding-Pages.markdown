---
layout: post
title: OS X 下使用 Jekyll 和 Coding Pages 搭建静态博客
date: 2016-03-01 09:00:00 -05:00
categories:
  -- blog
---

Jekyll 是一个免费的简单静态网页生成工具，可以配合第三方服务例如 Disqus 实现一些扩展功能，不需要数据库支持。并且 Jekyll 可以部署在Github 或 Coding 上，可以绑定自己的域名，而且目前这是完全免费的。

1，Gem 安装/设置  
安装 Jekyll 需要用到包管理器 gem，该工具需要自行安装，gem -v 命令可查看本机是否已安装 gem。  
由于众所周知的原因，国内访问官方默认 gem sources 源速度不是十分理想（或者根本无法访问），所以建议切换成国内的，利用 gem sources -l 命令可查看当前 gem sources 源，然后利用以下命令将其替换为淘宝的（注意：这里的 http://rubygems.org/ 替换成当前 gem sources 源地址）：  
``
gem sources --remove http://rubygems.org/
``  
``
gem sources -a https://ruby.taobao.org/
``

2，安装 Jekyll 到本地  
因为打算在 Coding Pages 上搭建，根据 [Coding 帮助文档](https://coding.net/help/doc/pages/index.html)，Coding Pages 目前支持 jekyll 2.4.0，所以我们需要指定版本安装 Jekyll，
接下来，终端执行以下命令：  
``
sudo gem install jekyll -v '2.4.0'
``  
输入密码后等待安装完成，执行以下命令尝试查看 Jekyll 版本号：  
``
jekyll -v
``  
若能正确显示版本号 jekyll 2.4.0 表示安装成功。  

3，搭建博客  
手动编写的话可以参考：[这篇博文](http://www.blogways.net/blog/2013/04/13/jekyll-usage.html)；  
同时网上有大量开发者们分享的模板可供选择使用，  
[Jekyll Themes](http://jekyllthemes.org/)  
[Github Jekyll Sites](https://github.com/jekyll/jekyll/wiki/Sites)  
本博客的搭建我选择了在该[模板](https://github.com/sl4m/skim.cc)的基础上进行修改，在这里对原作者表示感谢，🙏  

4，本地预览效果  
在终端中用 cd 命令切换到博客所在目录，执行 jekyll server 命令启动本地服务器，若启动成功可在浏览器中访问 http://0.0.0.0:4000/ 进行预览。  

5，上传到 Coding Pages  
在 Coding 新建一个项目，将博客所在项目 push 到新建的项目中，推荐的做法是创建一个新的 coding-pages 分支来作为启动 Coding Pages 之用，然后切换到 Pages 标签，开启 pages 服务，这时 Coding 会提供一个类似 {user_name}.coding.me/{project_name} 的链接用于访问，例如本博客的是：  
``
http://eyrefree.coding.me/blog.eyrefree.org
``  

6，绑定域名  
默认提供的链接可能过长或者不便于日常使用，我们也可以绑定自己的域名。  
首先，打开自己的域名控制面板，新建一个 CNAME 解析到 {user_name}.coding.me，例如我的是将 blog.eyrefree.org 解析到 eyrefree.coding.me；  
然后，打开 Coding 项目页面切换到 pages 项，填入刚才的设置解析的域名 blog.eyrefree.org，点击“添加域名绑定”按钮即可，在浏览器中直接访问 blog.eyrefree.org 就能成功打开啦（有时可能由于缓存或者解析时间的问题，稍等片刻即可）。  

7，编写博文  
接下来就是日常编写博文啦，一般是 markdown 格式的，编写完成后 push 到 Coding 服务器即可。  
    
    
以上，😝，欢迎继续关注[我的博客](http://blog.eyrefree.org)，感谢，🙏  
