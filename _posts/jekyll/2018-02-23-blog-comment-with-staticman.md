---
title: "为博客添加staticman评论组件"
categories: ruby  
tags: jekyll
---
## 工具选择

其实mistake主题中给出了很多的选项：

| Name             | Comment Provider          |
| ---------------- | ------------------------- |
| **disqus**       | Disqus                    |
| **discourse**    | Discourse                 |
| **facebook**     | Facebook Comments         |
| **google-plus**  | Google+ Comments          |
| **staticman_v2** | Staticman v2              |
| **staticman**    | Staticman v1 (deprecated) |
| **custom**       | Other                     |

由于蛤的力量，disqus国内访问不到

discourse太过庞大了，毕竟是以论坛的目标的

facebook同第一条

google-plus同第一条

staticman居然成了最终选项 <@_@>

## staticman 官网
[官网](https://staticman.net)

[手册](https://staticman.net/docs/)
英语大拿请自行阅读，不想看的请掠过，后面有神翻译


## staticman 使用

### 一、将Staticman添加项目仓库

打开github中需要添加的项目，进入设置页面

上图

搜索后点击右边的 Add Collaborator按钮，稍微等一下，上面就多了这个应用

然后访问这个地址（注意替换花括号中的内容）：https://api.staticman.net/v2/connect/{your GitHub username}/{your repository name}

成功会得到一个ok，真的只有ok，在左上角，眼神不好的童鞋别看漏了

### 二、mistake主题中的 staticman 配置



文档乱七八糟，于是我用find大法，直接找到了staticman主题中的comment.html文件

可以跳过阅读start
---

文件内容如下(可跳过阅读):
```html
{\% when "staticman_v2" \%}
      <section id="static-comments">
        {\% if site.repository and site.staticman.branch \%}
          <!-- Start static comments -->
          <div class="js-comments">
            {\% if site.data.comments[page.slug] \%}
              <h4 class="page__comments-title">{{ site.data.ui-text[site.locale].comments_title | default: "Comments" }}</h4>
              {\% assign comments = site.data.comments[page.slug] | sort \%}

              {\% for comment in comments \%}
                {\% assign email = comment[1].email \%}
                {\% assign name = comment[1].name \%}
                {\% assign url = comment[1].url \%}
                {\% assign date = comment[1].date \%}
                {\% assign message = comment[1].message \%}
                {\% include comment.html index=forloop.index email=email name=name url=url date=date message=message \%}
              {\% endfor \%}
            {\% endif \%}
          </div>
          <!-- End static comments -->

          <!-- Start new comment form -->
            ...
          <!-- End new comment form -->
          {\% if site.reCaptcha.siteKey \%}<script async src="https://www.google.com/recaptcha/api.js"></script>{\% endif \%}
        {\% endif \%}
      </section>
```

引入这个文件的地方在single.html这种布局文件
```html
{\% if jekyll.environment == 'production' and site.comments.provider and page.comments \%}
      {\% include comments.html \%}
{\% endif \%}
```

可以跳过阅读end
---

上面的文件给了海量信息：

1. jekyll的运行环境为线上模式--production

2. _config.yml的以下配置必须有：

    + site.comments.provider
    
    + page.comments
    
    + site.repository
    
    + site.staticman.branch

3. 示例文件：

   [staticman.yml](https://github.com/mmistakes/minimal-mistakes/blob/master/staticman.yml)

   [_config.yml](https://github.com/dark-wind/dark-wind.github.io/blob/master/_config.yml)

   强调一下，这2个文件都必须要有，否则提交评论的时候会报错，报错的解决方法请到官方的issue中搜索，大部分给出了解决方案

4.为文章开启评论功能
配置文章的布局（Layouts）
```html
comments: true
```

eg:
```html

---
title: "为博客添加staticman评论组件"
categories: ruby
tags: jekyll
comments: true
---
```