---
title: "Git 常用命令速查"
categories: tools
tags: git
---

**Git 常用命令速查**

git branch 查看本地所有分支
git status 查看当前状态&nbsp;
git commit 提交&nbsp;
git branch -a 查看所有的分支
git branch -r 查看远程所有分支
git commit -am "init" 提交并且加注释&nbsp;
git remote add origin git@192.168.1.119:ndshow
git push origin master 将文件给推到服务器上&nbsp;
git remote show origin 显示远程库origin里的资源&nbsp;
git push origin master:develop
git push origin master:hb-dev 将本地库与服务器上的库进行关联&nbsp;
git checkout --track origin/dev 切换到远程dev分支
git branch -D master develop 删除本地库develop
git checkout -b dev 建立一个新的本地分支dev
git merge origin/dev 将分支dev与当前分支进行合并
git checkout dev 切换到本地dev分支
git remoteshow 查看远程库
git add .
git rm 文件名(包括路径) 从git中删除指定文件
git clone git://github.com/schacon/grit.git 从服务器上将代码给拉下来
git config --list 看所有用户
git ls-files 看已经被提交的
git rm [file name] 删除一个文件
gitcommit -a 提交当前repos的所有的改变
git add [file name] 添加一个文件到git index
git commit -v 当你用－v参数的时候可以看commit的差异
git commit -m "This isthe message describing the commit" 添加commit信息
git commit -a -a是代表add，把所有的change加到git index里然后再commit
git commit -a -v 一般提交命令
git log 看你commit的日志
git diff 查看尚未暂存的更新
git rm a.a 移除文件(从暂存区和工作区中删除)
git rm --cached a.a 移除文件(只从暂存区中删除)
git commit -m "remove" 移除文件(从Git中删除)
git rm -f a.a 强行移除修改后文件(从暂存区和工作区中删除)
git diff --cached 或 $ git diff --staged 查看尚未提交的更新
git stash push 将文件给push到一个临时空间中
git stash pop 将文件从临时空间pop下来
---------------------------------------------------------
git remote add origin git@github.com:username/Hello-World.git
git push origin master 将本地项目给提交到服务器中
-----------------------------------------------------------
git pull 本地与服务器端同步
-----------------------------------------------------------------
git push (远程仓库名) (分支名) 将本地分支推送到服务器上去。
git push origin serverfix:awesomebranch
------------------------------------------------------------------
git fetch 相当于是从远程获取最新版本到本地，不会自动merge
git commit -a -m "log_message" (-a是提交所有改动，-m是加入log信息) 本地修改同步至服务器端 ：
git branch branch_0.1 master 从主分支master创建branch_0.1分支
git branch -m branch_0.1 branch_1.0 将branch_0.1重命名为branch_1.0
git checkout branch_1.0/master 切换到branch_1.0/master分支
du -hs

git branch 删除远程branch
git push origin :branch_remote_name
git branch -r -d branch_remote_name
-----------------------------------------------------------

初始化版本库，并提交到远程服务器端
mkdir WebApp
cd WebApp
git init 本地初始化
touch README
git add README 添加文件
git commit -m 'first commit'
git remote add origin git@github.com:daixu/WebApp.git

增加一个远程服务器端

上面的命令会增加URL地址为'git@github.com:daixu/WebApp.git'，名称为origin的远程服务器库，以后提交代码的时候只需要使用 origin别名即可

**二、 Git 命令速查表**

1、常用的Git命令

<tdstyle="margin: 0px;="" padding:="" 0.2em="" 0.46em;="" border-color:="" rgb(204,="" 204,="" 204);="" background:="" rgb(238,="" 238,="" 238);"="">

<span style="line-height: 21.6px;font-size: 12px; color: red;">git checkout</span>
</tdstyle="margin:><table class="jbborder"><thead><tr class="firstRow"><td width="200" style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(218, 238, 243);">

**<span style="line-height: 21.6px; font-size: 12px; color:rgb(78, 78, 78);">命令</span>**
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(218, 238, 243);">

**<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">简要说明</span>**
</td></tr></thead><tbody><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git add</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">添加至暂存区</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git add–interactive</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">交互式添加</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git apply</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204,204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">应用补丁</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git am</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">应用邮件格式补丁</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204,204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git annotate</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">同义词，等同于 git blame</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git archive</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">文件归档打包</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git bisect</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">二分查找</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git blame</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">文件逐行追溯</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git branch</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204);background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">分支管理</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git cat-file</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">版本库对象研究工具</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">检出到工作区、切换或创建分支</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git cherry-pick</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">提交拣选</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git citool</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">图形化提交，相当于 git gui&nbsp;</span>命令
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git clean</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">清除工作区未跟踪文件</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git clone</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">克隆版本库</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git commit</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height:21.6px; font-size: 12px; color: rgb(78, 78, 78);">提交</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git config</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">查询和修改配置</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git describe</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">通过里程碑直观地显示提交ID</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git diff</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204,204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">差异比较</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git difftool</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">调用图形化差异比较工具</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color:rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git fetch</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">获取远程版本库的提交</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color:rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git format-patch</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">创建邮件格式的补丁文件。参见 gitam&nbsp;</span>命令
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git grep</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em;border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);"><pstyle="text-align:left;padding-top: 5px;="" padding-bottom:="" 5px;"=""><span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">文件内容搜索定位工具</span></pstyle="text-align:left;padding-top:></td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git gui</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">基于Tcl/Tk</span>的图形化工具，侧重提交等操作
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git help</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">帮助</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git init</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em;border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);"><pstyle="text-align:left;padding-top: 5px;="" padding-bottom:="" 5px;"=""><span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">版本库初始化</span></pstyle="text-align:left;padding-top:></td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git init-db*</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">同义词，等同于 git init</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git log</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">显示提交日志</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238,238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git merge</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">分支合并</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git mergetool</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">图形化冲突解决</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git mv</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">重命名</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git pull</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">拉回远程版本库的提交</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git push</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">推送至远程版本库</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git rebase</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height:21.6px; font-size: 12px; color: rgb(78, 78, 78);">分支变基</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color:rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git rebase–interactive</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">交互式分支变基</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git reflog</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color:rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">分支等引用变更记录管理</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git remote</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">远程版本库管理</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git repo-config*</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">同义词，等同于 git config</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git reset</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em;border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);"><pstyle="text-align:left;padding-top: 5px;="" padding-bottom:="" 5px;"=""><span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">重置改变分支“</span>游标”指向</pstyle="text-align:left;padding-top:></td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git rev-parse</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">将各种引用表示法转换为哈希值等</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git revert</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">反转提交</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git rm</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">删除文件</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git show</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">显示各种类型的对象</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git stage*</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">同义词，等同于 git add</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git stash</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<spanstyle="line-height: 21.6px;="" font-size:="" 12px;="" color:="" rgb(78,="" 78,="" 78);"="">保存和恢复进度</spanstyle="line-height:>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">gitstatus</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">显示工作区文件状态</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">gittag</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">里程碑管理</span>
</td></tr></tbody></table>

2、对象库操作相关命令

<table class="jbborder"><thead><tr class="firstRow"><td width="200" style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(218, 238, 243);">

**<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">命令</span>**
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(218, 238, 243);">

**<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">简要说明</span>**
</td></tr></thead><tbody><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git commit-tree</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">从树对象创建提交</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git hash-object</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">从标准输入或文件计算哈希值或创建对象</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<spanstyle="line-height: 21.6px;="" font-size:="" 12px;="" color:="" red;"="">git ls-files</spanstyle="line-height:>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">显示工作区和暂存区文件</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git ls-tree</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">显示树对象包含的文件</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git mktag</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">读取标准输入创建一个里程碑对象</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git mktree</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">读取标准输入创建一个树对象</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git read-tree</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">读取树对象到暂存区</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color:red;">git update-index</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238,238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">工作区内容注册到暂存区及暂存区管理</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git unpack-file</span>
</td><td style="margin:0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">创建临时文件包含指定 blob&nbsp;</span>的内容
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git write-tree</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204,204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">从暂存区创建一个树对象</span>
</td></tr></tbody></table>

3、引用操作相关命令

<table class="jbborder"><thead><tr class="firstRow"><td width="200" style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(218, 238, 243);">

**<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">命令</span>**
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(218, 238, 243);">

**<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">简要说明</span>**
</td></tr></thead><tbody><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git check-ref-format</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">检查引用名称是否符合规范</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git for-each-ref</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">引用迭代器，用于shell</span>编程
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git ls-remote</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">显示远程版本库的引用</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git name-rev</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">将提交ID</span>显示为友好名称
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git peek-remote*</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">过时命令，请使用 git ls-remote</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git rev-list</span>
</td><td style="margin: 0px; padding:0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">显示版本范围</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git show-branch</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">显示分支列表及拓扑关系</span>
</td></tr><tr><td style="margin:0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git show-ref</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">显示本地引用</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git symbolic-ref</span>
</td><td style="margin: 0px;padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">显示或者设置符号引用</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git update-ref</span>
</td><td style="margin:0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">更新引用的指向</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204);background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git verify-tag</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">校验 GPG&nbsp;</span>签名的Tag
</td></tr></tbody></table>

4、版本库管理相关命令

<tdstyle="margin: 0px;="" padding:="" 0.2em="" 0.46em;="" border-color:="" rgb(204,="" 204,="" 204);="" background:="" rgb(238,="" 238,="" 238);"="">

<span style="line-height: 21.6px;font-size: 12px; color: red;">git unpack-objects</span>
</tdstyle="margin:><table class="jbborder"><thead><tr class="firstRow"><td width="200" style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(218, 238, 243);">

**<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">命令</span>**
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(218, 238, 243);">

**<spanstyle="line-height: 21.6px;="" font-size:="" 12px;="" color:="" rgb(78,="" 78,="" 78);"="">简要说明</spanstyle="line-height:>**
</td></tr></thead><tbody><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git count-objects</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">显示松散对象的数量和磁盘占用</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204,204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git filter-branch</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">版本库重构</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git fsck</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">对象库完整性检查</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204,204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git fsck-objects*</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">同义词，等同于 git fsck</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color:rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git gc</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204,204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">版本库存储优化</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git index-pack</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">从打包文件创建对应的索引文件</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git lost-found*</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">过时，请使用 git fsck –lost-found&nbsp;</span>命令
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git pack-objects</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">从标准输入读入对象ID</span>，打包到文件
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git pack-redundant</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size:12px; color: rgb(78, 78, 78);">查找多余的 pack&nbsp;</span>文件
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height:21.6px; font-size: 12px; color: red;">git pack-refs</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">将引用打包到 .git/packed-refs&nbsp;</span>文件中
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git prune</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">从对象库删除过期对象</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git prune-packed</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">将已经打包的松散对象删除</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git relink</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">为本地版本库中相同的对象建立硬连接</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background:rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git repack</span>
</td><td style="margin: 0px; padding:0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">将版本库未打包的松散对象打包</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git show-index</span>
</td><td style="margin: 0px;padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">读取包的索引文件，显示打包文件中的内容</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">从打包文件释放文件</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height:21.6px; font-size: 12px; color: red;">git verify-pack</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">校验对象库打包文件</span>
</td></tr></tbody></table>

5、数据传输相关命令

<table class="jbborder"><thead><tr class="firstRow"><td width="200" style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(218, 238, 243);">

**<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">命令</span>**
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(218, 238, 243);">

**<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78,78);">简要说明</span>**
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(218, 238, 243);">
</td></tr></thead><tbody><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git fetch-pack</span>
</td><td colspan="2" style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px;color: rgb(78, 78, 78);">执行 git fetch&nbsp;</span>或 git pull 命令时在本地执行此命令，用于从其他版本库获取缺失的对象
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git receive-pack</span>
</td><td colspan="2" style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">执行 git push&nbsp;</span>命令时在远程执行的命令，用于接受推送的数据
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git send-pack</span>
</td><td colspan="2" style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">执行 git push&nbsp;</span>命令时在本地执行的命令，用于向其他版本库推送数据
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git upload-archive</span>
</td><td colspan="2" style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204,204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">执行 git archive –remote&nbsp;</span>命令基于远程版本库创建归档时，远程版本库执行此命令传送归档
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git upload-pack</span>
</td><td colspan="2" style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204,204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">执行 git fetch&nbsp;</span>或 git pull 命令时在远程执行此命令，将对象打包、上传
</td></tr></tbody></table>

6、邮件相关命令

<tdstyle="margin: 0px;="" padding:="" 0.2em="" 0.46em;="" border-color:="" rgb(204,="" 204,="" 204);="" background:="" rgb(238,="" 238,="" 238);"="">

<span style="line-height: 21.6px;font-size: 12px; color: rgb(78, 78, 78);">创建包含提交间差异和执行PULL</span>操作地址的信息
</tdstyle="margin:><table class="jbborder"><thead><tr class="firstRow"><td width="200" style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(218, 238, 243);">

**<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">命令</span>**
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(218, 238, 243);">

**<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">简要说明</span>**
</td></tr></thead><tbody><tr><td style="margin: 0px; padding: 0.2em 0.46em;border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);"><pstyle="text-align:left;padding-top: 5px;="" padding-bottom:="" 5px;"=""><span style="line-height: 21.6px; font-size: 12px; color: red;">git imap-send</span></pstyle="text-align:left;padding-top:></td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">将补丁通过 IMAP&nbsp;</span>发送
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git mailinfo</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">从邮件导出提交说明和补丁</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git mailsplit</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238,238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">将 mbox&nbsp;</span>或 Maildir 格式邮箱中邮件逐一提取为文件
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204,204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git request-pull</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git send-email</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">发送邮件</span>
</td></tr></tbody></table>

7、协议相关命令

<table class="jbborder"><thead><tr class="firstRow"><td width="200" style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(218, 238, 243);">

**<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">命令</span>**
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(218, 238, 243);">

**<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">简要说明</span>**
</td></tr></thead><tbody><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git daemon</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">实现Git</span>协议
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204,204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git http-backend</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">实现HTTP</span>协议的CGI程序，支持智能HTTP协议
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git instaweb</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color:rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">即时启动浏览器通过 gitweb&nbsp;</span>浏览当前版本库
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git shell</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">受限制的shell</span>，提供仅执行Git命令的SSH访问
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size:12px; color: red;">git update-server-info</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">更新哑协议需要的辅助文件</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204,204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git http-fetch</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">通过HTTP</span>协议获取版本库
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git http-push</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">通过HTTP/DAV</span>协议推送
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git remote-ext</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">由Git</span>命令调用，通过外部命令提供扩展协议支持
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git remote-fd</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">由Git</span>命令调用，使用文件描述符作为协议接口
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git remote-ftp</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">由Git</span>命令调用，提供对FTP协议的支持
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204,204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git remote-ftps</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">由Git</span>命令调用，提供对FTPS协议的支持
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git remote-http</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">由Git</span>命令调用，提供对HTTP协议的支持
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git remote-https</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">由Git</span>命令调用，提供对HTTPS协议的支持
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git remote-testgit</span>
</td><td style="margin: 0px;padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">协议扩展示例脚本</span>
</td></tr></tbody></table>

8、版本库转换和交互相关命令

<table class="jbborder"><thead><tr class="firstRow"><td width="200" style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(218, 238, 243);">

**<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">命令</span>**
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(218, 238, 243);">

**<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">简要说明</span>**
</td></tr></thead><tbody><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git archimport</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238,238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">导入Arch</span>版本库到Git
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background:rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git bundle</span>
</td><td style="margin: 0px; padding:0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">提交打包和解包，以便在不同版本库间传递</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git cvsexportcommit</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">将Git</span>的一个提交作为一个CVS检出
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git cvsimport</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">导入CVS</span>版本库到Git。或者使用 cvs2git
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<spanstyle="line-height: 21.6px;="" font-size:="" 12px;="" color:="" red;"="">git cvsserver</spanstyle="line-height:>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">Git</span><span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">的CVS</span>协议模拟器，可供CVS命令访问Git版本库
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204);background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git fast-export</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">将提交导出为 git-fast-import&nbsp;</span>格式
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git fast-import</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">其他版本库迁移至Git</span>的通用工具
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git svn</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">Git&nbsp;</span><span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">作为前端操作 Subversion</span>
</td></tr></tbody></table>

9、合并相关的辅助命令

<tableclass="jbborder">

**<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">命令</span>**

**<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">简要说明</span>**

<span style="line-height: 21.6px; font-size: 12px; color: red;">git merge-base</span>

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">供其他脚本调用，找到两个或多个提交最近的共同祖先</span>

<span style="line-height: 21.6px; font-size: 12px; color: red;">git merge-file</span>

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">针对文件的两个不同版本执行三向文件合并</span>

<span style="line-height: 21.6px; font-size: 12px; color: red;">git merge-index</span>

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">对index</span>中的冲突文件调用指定的冲突解决工具

<span style="line-height: 21.6px; font-size: 12px; color: red;">git merge-octopus</span>

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">合并两个以上分支。参见 git merge&nbsp;</span>的octopus合并策略

<span style="line-height: 21.6px; font-size: 12px; color: red;">git merge-one-file</span>

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">由 git merge-index&nbsp;</span>调用的标准辅助程序

<span style="line-height: 21.6px; font-size: 12px; color: red;">git merge-ours</span>

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">合并使用本地版本，抛弃他人版本。参见 git merge&nbsp;</span>的ours合并策略

<span style="line-height: 21.6px; font-size: 12px; color: red;">git merge-recursive</span>

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">针对两个分支的三向合并。参见 git merge&nbsp;</span>的recursive合并策略

<span style="line-height: 21.6px; font-size: 12px; color: red;">git merge-resolve</span>

<spanstyle="line-height: 21.6px;="" font-size:="" 12px;="" color:="" rgb(78,="" 78,="" 78);"="">针对两个分支的三向合并。参见 git merge&nbsp;的resolve合并策略</spanstyle="line-height:>

<span style="line-height: 21.6px; font-size: 12px; color: red;">git merge-subtree</span>

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">子树合并。参见 git merge&nbsp;</span>的 subtree 合并策略

<span style="line-height: 21.6px; font-size: 12px; color: red;">gitmerge-tree</span>

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">显式三向合并结果，不改变暂存区</span>

<span style="line-height: 21.6px; font-size: 12px; color:red;">git fmt-merge-msg</span>

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">供执行合并操作的脚本调用，用于创建一个合并提交说明</span>

<span style="line-height: 21.6px; font-size: 12px; color: red;">git rerere</span>

<span style="line-height: 21.6px; font-size:12px; color: rgb(78, 78, 78);">重用所记录的冲突解决方案</span>

10、 杂项

<table class="jbborder"><thead><tr class="firstRow"><td width="200" style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(218, 238, 243);">

**<span style="line-height:21.6px; font-size: 12px; color: rgb(78, 78, 78);">命令</span>**
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(218, 238, 243);">

**<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">简要说明</span>**
</td></tr></thead><tbody><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git bisect–helper</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">由 git bisect&nbsp;</span>命令调用，确认二分查找进度
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git check-attr</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">显示某个文件是否设置了某个属性</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git checkout-index</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">从暂存区拷贝文件至工作区</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<spanstyle="line-height: 21.6px;="" font-size:="" 12px;="" color:="" red;"="">git cherry</spanstyle="line-height:>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">查找没有合并到上游的提交</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git diff-files</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">比较暂存区和工作区，相当于 git diff –raw</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px;color: red;">git diff-index</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">比较暂存区和版本库，相当于 git diff –cached –raw</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color:rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git diff-tree</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">比较两个树对象，相当于 git diff –raw A B</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">gitdifftool–helper</span>
</td><td style="margin: 0px; padding: 0.2em0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">由 git difftool&nbsp;</span>命令调用，默认要使用的差异比较工具
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git get-tar-commit-id</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204,204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">从 git archive&nbsp;</span>创建的 tar 包中提取提交ID
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git gui–askpass</span>
</td><td style="margin: 0px; padding: 0.2em0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">命令 git gui&nbsp;</span>的获取用户口令输入界面
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204);background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git notes</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">提交评论管理</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size:12px; color: red;">git patch-id</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background:rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">补丁过滤行号和空白字符后生成补丁唯一ID</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git quiltimport</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">将Quilt</span>补丁列表应用到当前分支
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git replace</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">提交替换</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git shortlog</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">对 git log&nbsp;</span>的汇总输出，适合于产品发布说明
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git stripspace</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<spanstyle="line-height: 21.6px;="" font-size:="" 12px;="" color:="" rgb(78,="" 78,="" 78);"="">删除空行，供其他脚本调用</spanstyle="line-height:>
</td></tr><tr><td style="margin: 0px; padding:0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git submodule</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78,78);">子模组管理</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git tar-tree</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">过时命令，请使用 git archive</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px;color: red;">git var</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">显示 Git&nbsp;</span>环境变量
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git web–browse</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background:rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">启动浏览器以查看目录或文件</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git whatchanged</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">显示提交历史及每次提交的改动</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git-mergetool–lib</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">包含于其他脚本中，提供合并/</span>差异比较工具的选择和执行
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git-parse-remote</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">包含于其他脚本中，提供操作远程版本库的函数</span>
</td></tr><tr><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: red;">git-sh-setup</span>
</td><td style="margin: 0px; padding: 0.2em 0.46em; border-color: rgb(204, 204, 204); background: rgb(238, 238, 238);">

<span style="line-height: 21.6px; font-size: 12px; color: rgb(78, 78, 78);">包含于其他脚本中，提供 shell&nbsp;</span>编程的函数库
</td></tr></tbody></table>

