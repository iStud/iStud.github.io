---
layout: article
title: 用 jekyll 和 github pages 搭建博客及遇到的问题
tags: jekyll  github-pages 
modify_date: 2023-03-20
---
### 搭建博客的大概步骤

1.  注册一个 GitHub 账号（如果你还没有）。
2.  fork 一个 jekyll 主题仓库，起名为：`your_username.github.io`，访问 http://your_username.github.io来查看博客的效果，注意用户名称别写错了。
3.  为了有预览功能需要配置一些环境
    1. 装 ruby `brew install ruby`
    2. 装 bundle `gem install bundle`
    3. 在仓库主目录安装主题所需 Jekyll 插件 `bundle install`
    4. 预览 `bundle exec jekyll serve`

### 遇到的一些问题

- 安装 RVM，RVM 是 Ruby 版本管理器，它可以帮助您安装，管理和切换不同版本的 Ruby。在终端中输入以下命令来安装 RVM：

```
curl -sSL https://get.rvm.io | bash -s stable
```

安装完成后，您需要重新启动终端。

- 安装最新的 Ruby，在终端中执行以下命令来安装最新的 Ruby：

```
rvm install ruby --latest
```

- 如果您已经安装了多个 Ruby 版本，可以使用以下命令来查看所有已安装的 Ruby 版本：

```
rvm list
```

- 可以使用以下命令来切换使用不同的 Ruby 版本：

```
rvm use <ruby-version>
```

- 报 `jekyll error building page related to kramdown parser` 无法预览问题
   1. delete the Gemfile.lock file
   2. go to Gemfile file add gem "kramdown-parser-gfm"
   3. ran bundle install.
   4. bundle exec jekyll serve
