---
layout: post
title: 安装Jekyll的辛酸路！
category: other
tags: [other]
excerpt: 记录Win7安装Jekyll的过程
keywords: Ruby,Jekyll
---

jekyll是一个基于ruby的博客系统，对于喜欢折腾的我决定来试一试，果然。。。没有令我失望，它很折腾。好在最终鼓捣成功了，记录一下，终于开启写博客的这扇大门了。哈哈哈

## 依赖组件

### 1，安装Ruby 

下载安装exe，地址：[http://rubyinstaller.org/downloads/](http://rubyinstaller.org/downloads/)

根据自己的机型选择对应的安装包(**划重点，因后续有需要安装不同的gem，我发现好多因为ruby版本问题装不了，所以在这推荐使用2,2,4版本的**)

![img]({{ site.url }}/assets/images/2019/other/install-ruby.jpg)

安装的注意点：

自动帮你配置环境变量，要安装在根目录

![img]({{ site.url }}/assets/images/2019/other/install-ruby (2).jpg)

测试是否安装完成：

ruby -v

我的输出结果是

ruby 2.3.0p0 (2015-12-25 revision 53290) [x64-mingw32]

### 2，安装Devkit

![img]({{ site.url }}/assets/images/2019/other/install-ruby (3).jpg)

1），运行安装包并解压缩至某文件夹，如 C:\DevKit

2），通过初始化来创建 config.yml 文件。在命令行窗口内，输入下列命令：

cd “C:\DevKit”

ruby dk.rb init

notepad config.yml

3），在打开的记事本窗口中，于末尾添加新的一行- C:\Ruby200-x64，保存文件并退出。

4），回到命令行窗口内，审查（非必须）并安装。

ruby dk.rb review

ruby dk.rb install


### 3，安装jekyll 

先查看你的gem是否安装完毕：

gem -v

gem install jekyll

测试是否安装完毕：

![img]({{ site.url }}/assets/images/2019/other/install-ruby (4).jpg)

新建jekyll 项目

jekyll new myblog

cd myblog

运行jekyll 项目： 官方文档（[http://jekyllrb.com/docs/quickstart/](https://link.jianshu.com/?t=http://jekyllrb.com/docs/quickstart/)）

jekyll s  / jekyll serve

如果报错，按照提示，安装相关的gem

![img]({{ site.url }}/assets/images/2019/other/install-ruby (5).jpg)

最终成功运行！

![img]({{ site.url }}/assets/images/2019/other/install-ruby (6).jpg)

最终通过本地4000端口访问

## 常见问题

> 通过gem安装依赖项时，您可能会遇到一些错误，具体取决于您的环境。

> 有关SSL_connect的错误。请检查 [here](http://stackoverflow.com/questions/15305350/gem-install-fails-with-openssl-failure) 和 [here](http://railsapps.github.io/openssl-certificate-verify-failed.html)

> gem下载速度慢，请更换国内的源，例如：http://gems.ruby-china.com

我本地.gemrc配置(gem的配置文件)
```
---
:backtrace: false
:bulk_threshold: 1000
:sources:
# ruby-china 的源，下载速度很快
- http://gems.ruby-china.com
:update_sources: true
:verbose: true
:concurrent_downloads: 8
# 忽略SSL_CONNECT错误
:ssl_verify_mode: 0 

```

