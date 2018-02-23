---
title: "为博客添加staticman评论组件"
categories: ruby  
tags: jekyll
comments: true
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
https://staticman.net

## staticman 使用

### 官网手册原文
英语大拿请自行阅读，不想看的请掠过，后面有神翻译

https://staticman.net/docs/

### 将Staticman添加项目仓库

打开github中需要添加的项目，进入设置页面

上图

搜索后点击右边的 Add Collaborator按钮，稍微等一下，上面就多了这个应用

然后访问这个地址（注意替换花括号中的内容）：https://api.staticman.net/v2/connect/{your GitHub username}/{your repository name}

成功会得到一个ok，真的只有ok，在左上角，眼神不好的童鞋别看漏了

### mistake主题中的 staticman 配置

文档乱七八糟，于是我用find大法，直接找到了staticman主题中的comment.html文件

可以跳过阅读start
===

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
          <div class="page__comments-form">
            <h4 class="page__comments-title">{{ site.data.ui-text[site.locale].comments_label | default: "Leave a Comment" }}</h4>
            <p class="small">{{ site.data.ui-text[site.locale].comment_form_info | default: "Your email address will not be published. Required fields are marked" }} <span class="required">*</span></p>
            <form id="new_comment" class="page__comments-form js-form form" method="post" action="https://api.staticman.net/v2/entry/{{ site.repository }}/{{ site.staticman.branch }}/comments">
              <div class="form__spinner">
                <i class="fas fa-spinner fa-spin fa-3x fa-fw"></i>
                <span class="sr-only">{{ site.data.ui-text[site.locale].loading_label | default: "Loading..." }}</span>
              </div>

              <div class="form-group">
                <label for="comment-form-message">{{ site.data.ui-text[site.locale].comment_form_comment_label | default: "Comment" }} <small class="required">*</small></label>
                <textarea type="text" rows="3" id="comment-form-message" name="fields[message]" tabindex="1"></textarea>
                <div class="small help-block"><a href="https://daringfireball.net/projects/markdown/">{{ site.data.ui-text[site.locale].comment_form_md_info | default: "Markdown is supported." }}</a></div>
              </div>
              <div class="form-group">
                <label for="comment-form-name">{{ site.data.ui-text[site.locale].comment_form_name_label | default: "Name" }} <small class="required">*</small></label>
                <input type="text" id="comment-form-name" name="fields[name]" tabindex="2" />
              </div>
              <div class="form-group">
                <label for="comment-form-email">{{ site.data.ui-text[site.locale].comment_form_email_label | default: "Email address" }} <small class="required">*</small></label>
                <input type="email" id="comment-form-email" name="fields[email]" tabindex="3" />
              </div>
              <div class="form-group">
                <label for="comment-form-url">{{ site.data.ui-text[site.locale].comment_form_website_label | default: "Website (optional)" }}</label>
                <input type="url" id="comment-form-url" name="fields[url]" tabindex="4"/>
              </div>
              <div class="form-group hidden" style="display: none;">
                <input type="hidden" name="options[slug]" value="{{ page.slug }}">
                <label for="comment-form-location">Not used. Leave blank if you are a human.</label>
                <input type="text" id="comment-form-location" name="fields[hidden]" autocomplete="off"/>
                <input type="hidden" name="options[reCaptcha][siteKey]" value="{{ site.reCaptcha.siteKey }}">
                <input type="hidden" name="options[reCaptcha][secret]" value="{{ site.reCaptcha.secret }}">
              </div>
              <!-- Start comment form alert messaging -->
              <p class="hidden js-notice">
                <strong class="js-notice-text"></strong>
              </p>
              <!-- End comment form alert messaging -->
              <div class="form-group">
                <div class="g-recaptcha" data-sitekey="{{ site.reCaptcha.siteKey }}"></div>
              </div>
              <div class="form-group">
                <button type="submit" id="comment-form-submit" tabindex="5" class="btn btn--primary btn--large">{{ site.data.ui-text[site.locale].comment_btn_submit | default: "Submit Comment" }}</button>
              </div>
            </form>
          </div>
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
===

上面的文件给了海量信息：

1 jekyll的运行环境为线上模式--production

2 _config.yml的以下配置必须有：

    + site.comments.provider
    
    + page.comments
    
    + site.repository
    
    + site.staticman.branch
