---
title:  "minimal mistake 本地运行ffi缺失问题修复"
categories: ruby minimal
tag: jekyll
toc: true
toc_label: 目录
---

minimal 基于jekyll
所以前面的安装步骤相同
## 基本依赖安装
```
sudo apt install ruby ruby-dev
sudo apt install bundler
sudo apt install gem
```

## eventmachine报错
```
darkwind@darkwind-pc:~/www/dark-wind.github.io$ bundle install
Fetching gem metadata from https://rubygems.org/...........
Fetching concurrent-ruby 1.0.5
Your user account isn't allowed to install to the system RubyGems.
  You can cancel this installation and run:

      bundle install --path vendor/bundle

  to install the gems into ./vendor/bundle/, or you can enter your password
  and install the bundled gems to RubyGems using sudo.

。。。。。省略若干

Installing eventmachine 1.2.5 with native extensions
Gem::Ext::BuildError: ERROR: Failed to build gem native extension.

。。。。。省略若干

extconf failed, exit code 1

Gem files will remain installed in
/var/lib/gems/2.5.0/gems/eventmachine-1.2.5 for inspection.
Results logged to
/var/lib/gems/2.5.0/extensions/x86_64-linux/2.5.0/eventmachine-1.2.5/gem_make.out

An error occurred while installing eventmachine (1.2.5), and
Bundler cannot continue.
Make sure that `gem install eventmachine -v '1.2.5'` succeeds before
bundling.
```
```
这里告诉我使用path参数来免去提权
bundle install --path vendor/bundle
```

## ffi报错

```
darkwind@darkwind-pc:~/www/dark-wind.github.io$ bundle install
Fetching gem metadata from https://rubygems.org/.........
Using concurrent-ruby 1.0.5
Using i18n 0.9.5

。。。。。。省略若干

Installing ffi 1.9.21 with native extensions
Gem::Ext::BuildError: ERROR: Failed to build gem native extension.

。。。。。。省略若干

make failed, exit code 2

Gem files will remain installed in
/tmp/bundler20190210-19239-nubfpaffi-1.9.21/gems/ffi-1.9.21 for inspection.
Results logged to
/tmp/bundler20190210-19239-nubfpaffi-1.9.21/extensions/x86_64-linux/2.5.0/ffi-1.9.21/gem_make.out

An error occurred while installing ffi (1.9.21), and Bundler
cannot continue.
Make sure that `gem install ffi -v '1.9.21'` succeeds before bundling.
```

## 问题修复
参考以下issue:

[libffi/libffi autogen error](https://github.com/libffi/libffi/issues/210)

[ffi (1.9.10) Error](https://github.com/mmistakes/minimal-mistakes/issues/230)

安装缺失库
```
sudo apt install libmysqlclient-dev
sudo apt-get install libltdl-dev
sudo gem install ffi -v '1.9.21'
```
再次运行
```
bundle install --path vendor/bundle
bundle exec jekyll serve
```