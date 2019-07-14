# dark-wind.github.io

## 本地运行环境搭建
1.安装ruby

系统自带了

2.安装bundle
```
$ gem install bundle
Fetching: bundler-2.0.2.gem (100%)
ERROR:  While executing gem ... (Gem::FilePermissionError)
    You don't have write permissions for the /Library/Ruby/Gems/2.3.0 directory.
```

方便起见。。提权吧
```
$ sudo gem install bundle
Password:
Fetching: bundler-2.0.2.gem (100%)
Successfully installed bundler-2.0.2
Fetching: bundle-0.0.1.gem (100%)
Successfully installed bundle-0.0.1
Parsing documentation for bundler-2.0.2
Installing ri documentation for bundler-2.0.2
Parsing documentation for bundle-0.0.1
Installing ri documentation for bundle-0.0.1
Done installing documentation for bundler, bundle after 7 seconds
2 gems installed
```

3.本地运行
```
bundle exec jekyll serve
```
