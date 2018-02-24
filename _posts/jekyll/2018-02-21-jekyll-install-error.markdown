---
title:  "jekyll 安装错误及解决"
categories: ruby
tag: jekyll
---

第一次用jekyll，因为基于ruby这门比较陌生的语言（听说日本用的多），有非常的多环境问题。
由于ruby的环境设置不太熟悉，很多地方用到了sudo提权。其实完全不必，但由于时间有限，又是不常使用的本地环境，暂时不做处理。

## jekyll和bundler环境错误

### 报错信息
```shell
darkwind@darkwind-PC:~/shadow/dark-wind.github.io$ ruby -v
ruby 2.3.3p222 (2016-11-21) [x86_64-linux-gnu]
darkwind@darkwind-PC:~/shadow/dark-wind.github.io$ gem -v
2.5.2
darkwind@darkwind-PC:~/shadow/dark-wind.github.io$ jekyll -v

WARN: Unresolved specs during Gem::Specification.reset:
      rb-fsevent (>= 0.9.4, ~> 0.9)
      ffi (< 2, >= 0.5.0)
WARN: Clearing out unresolved specs.
Please report a bug if this causes problems.
/var/lib/gems/2.3.0/gems/bundler-1.16.1/lib/bundler/spec_set.rb:88:in `block in materialize': Could not find minimal-mistakes-jekyll-4.10.0 in any of the sources (Bundler::GemNotFound)
	from /var/lib/gems/2.3.0/gems/bundler-1.16.1/lib/bundler/spec_set.rb:82:in `map!'
	from /var/lib/gems/2.3.0/gems/bundler-1.16.1/lib/bundler/spec_set.rb:82:in `materialize'
	from /var/lib/gems/2.3.0/gems/bundler-1.16.1/lib/bundler/definition.rb:170:in `specs'
	from /var/lib/gems/2.3.0/gems/bundler-1.16.1/lib/bundler/definition.rb:237:in `specs_for'
	from /var/lib/gems/2.3.0/gems/bundler-1.16.1/lib/bundler/definition.rb:226:in `requested_specs'
	from /var/lib/gems/2.3.0/gems/bundler-1.16.1/lib/bundler/runtime.rb:108:in `block in definition_method'
	from /var/lib/gems/2.3.0/gems/bundler-1.16.1/lib/bundler/runtime.rb:20:in `setup'
	from /var/lib/gems/2.3.0/gems/bundler-1.16.1/lib/bundler.rb:107:in `setup'
	from /var/lib/gems/2.3.0/gems/jekyll-3.7.2/lib/jekyll/plugin_manager.rb:50:in `require_from_bundler'
	from /var/lib/gems/2.3.0/gems/jekyll-3.7.2/exe/jekyll:11:in `<top (required)>'
	from /usr/local/bin/jekyll:22:in `load'
	from /usr/local/bin/jekyll:22:in `<main>'

```

### 解决方案

安装ruby-dev
```shell
sudo apt install ruby-dev
```

重新安装jekyll和bundler
```shell
sudo rm -r 2.3.0/
sudo gem install jekyll bundler
```

成功解决
```shell
darkwind@darkwind-PC:/var/lib/gems$ bundler -v
Bundler version 1.16.1
darkwind@darkwind-PC:/var/lib/gems$ jekyll -v
jekyll 3.7.2
```

