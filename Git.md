###git指令关系图
点击此处查看[git指令关系图](http://ndpsoftware.com/git-cheatsheet.html)

*****


###初始化
#####新建一个git代码库
<pre><code>$ git init</code></pre>
#####新建一个目录并且初始化为git代码库
<pre><code>$ git init 目录名称</code></pre>
#####克隆一个git代码库
<pre><code>$ git clone xxx.git</code></pre>

*****


###配置
#####配置文件
git的配置文件为.gitconfig，可以在用户目录下全局配置，也可以在项目目录下单独配置
#####显示git配置
<pre><code>$ git config --list</code></pre>
#####编辑git配置文件
<pre><code>$ git config -e --global</code></pre>
#####设置用户信息
<pre><code>$ git config --global user.name "name"</code></pre>
<pre><code>$ git config --global user.email "email"</code></pre>

*****


###添加、删除文件
#####添加文件
<pre><code>$ git add [file1] [file2] #添加多个文件，放入暂存</code></pre>
<pre><code>$ git add [dir] </code> #添加指定目录，放入暂存</pre>
<pre><code>$ git add . #添加当前目录所有文件，放入暂存</code></pre>
#####删除文件
<pre><code>$ git rm [file1] [file2] #删除文件，放入暂存</code></pre>
#####停止追踪指定文件
<pre><code>$ git rm --cached [file] #文件依旧会保存在工作区</code></pre>
#####修改文件名
<pre><code>$ git mv file file-renamed</code></pre>

*****


###代码提交
#####提交暂存到仓库
<pre><code>$ git commit -m "信息"</code></pre>
<pre><code>$ git commit [file1] [file2] -m "信息" #提交多个文件到仓库</code></pre>
<pre><code>$ git commit -a #提交从上次commit之后的变化到仓库区</code></pre>
<pre><code>$ git commit -v #提交时显示所有diff信息</code></pre>
<pre><code>$ git commit --amend -m "信息" #使用一次新的commit，替代上一次的提交，如果代码没有任何变化，则用来改写上一次commit的提交信息</code></pre>
#####
<pre><code>$ git commit --amend [file1] [file2] #重做上一次commit,并包括指定文件的新变化</code></pre>

*****


###分支
#####列出所有本地分支
<pre><code>$ git branch</code></pre>
#####列出所有远程分支
<pre><code>$ git branch -r</code></pre>
#####列出所有本地和远程分支
<pre><code>$ git branch -a</code></pre>
#####新建一个分支，但依旧停留在当前分支
<pre><code>$ git branch 分支名称</code></pre>
#####新建一个分支，并切换到新分支
<pre><code>$ git checkout -b 分支名称</code></pre>
#####新建一个分支，指向指定的commit
<pre><code>$ git branch 分支名称 commit名称</code></pre>
#####新建一个分支，与某个远程分支建立追踪
<pre><code>$ git branch --track 分支名称 远程分支名称</code></pre>
#####切换到指定分支，并更新工作区
<pre><code>$ git checkout 分支名称</code></pre>
#####建立追踪关系，在现有分支和指定远程分支之间
<pre><code>$ git branch --set-upstream 分支名称 远程分支名称</code></pre>
#####合并指定分支到当前分支
<pre><code>$ git merge 分支名称</code></pre>
#####选择一个commit，合并进当前分支
<pre><code>$ git cherry-pick commit名称</code></pre>
#####删除分支
<pre><code>$ git branch -d 分支名称</code></pre>
#####删除远程分支
<pre><code>$ git push origin --delete 分支名称</code></pre>
<pre><code>$ git branch -dr 远程分支名称</code></pre>

*****


###标签
#####列出所有标签
<pre><code>$ git tag</code></pre>
#####新建一个标签在当前commit
<pre><code>$ git tag 标签名称</code></pre>
#####新建一个标签在指定的commit
<pre><code>$ git tag 标签名称 commit名称</code></pre>
#####删除本地标签
<pre><code>$ git tag -d 标签名称</code></pre>
#####删除远程标签
<pre><code>$ git push origin :refs/tags/标签名称</code></pre>
#####查看标签信息
<pre><code>$ git show 标签名称</code></pre>
#####提交指定的标签
<pre><code>$ git push [remote] 标签名称</code></pre>
#####提交所有标签
<pre><code>$ git push [remote] --tags</code></pre>
#####新建一个分支，指向某个tag
<pre><code>$ git checkout -b 分支名称 标签名称</code></pre>

*****


###查看信息
#####显示有变更的文件
<pre><code>$ git status</code></pre>
#####显示当前分支的版本历史
<pre><code>$ git log</code></pre>
#####显示commit历史，以及每次commit发生变更的文件
<pre><code>$ git log --stat</code></pre>
#####显示某个commit之后的所有变动，每个commit占据一行
<pre><code>$ git log 标签名称 HEAD --pretty=format:%s</code></pre>
#####显示某个commit之后的所有变动，其"提交说明"必须符合搜索条件
<pre><code>$ git log 标签名称 HEAD --grep feature</code></pre>
#####显示某个文件的历史版本，包括文件改名
<pre><code>$ git log --follow 文件名</code></pre>
<pre><code>$ git whatchanged 文件名</code></pre>
#####显示指定文件相关的每一次diff
<pre><code>$ git log -p 文件名</code></pre>
#####显示指定文件是什么人在什么时候修改过的
<pre><code>$ git blame 文件名</code></pre>
#####显示暂存区和工作区的差异
<pre><code>$ git diff</code></pre>
#####显示暂存区和上一个commit的差异
<pre><code>$ git diff --cached 文件名</code></pre>
#####显示工作区与当前分支最新commit之间的差异
<pre><code>$ git diff HEAD</code></pre>
#####显示两次提交之间的差异
<pre><code>$ git diff [first-branch] [second-branch]</code></pre>
#####显示某次提交的元数据和内容变化
<pre><code>$ git show commit名称</code></pre>
#####显示某次提交发生变化的文件
<pre><code>$ git show --name-only commit名称</code></pre>
#####显示某次提交时，某个文件的内容
<pre><code>$ git show [commit]:[filename]</code></pre>
#####显示当前分支的最近几次提交
<pre><code>$ git reflog</code></pre>

*****


###远程同步
#####下载远程仓库的所有变动
<pre><code>$ git fetch [remote]</code></pre>
#####显示所有远程仓库
<pre><code>$ git remote -v</code></pre>
#####显示某个远程仓库的信息
<pre><code>$ git remote show [remote]</code></pre>
#####增加一个新的远程仓库，并命名
<pre><code>$ git remote add [shortname] [url]</code></pre>
#####取回远程仓库的变化，并与本地分支合并
<pre><code>$ git pull [remote] [branch]</code></pre>
#####上传本地指定分支到远程仓库
<pre><code>$ git push [remote] [branch]</code></pre>
#####强行推送当前分支到远程仓库，即使有冲突
<pre><code>$ git push [remote] --force</code></pre>
#####推送所有分支到远程仓库
<pre><code>$ git push [remote] --all</code></pre>

*****


###撤销
#####恢复暂存区的指定文件到工作区
<pre><code>$ git checkout [file]</code></pre>
#####恢复某个commit的指定文件到暂存区和工作区
<pre><code>$ git checkout [commit] [file]</code></pre>
#####恢复暂存区的所有文件到工作区
<pre><code>$ git checkout .</code></pre>
#####重置暂存区的指定文件，与上一次commit保持一致，但工作区不变
<pre><code>$ git reset [file]</code></pre>
#####重置暂存区与工作区，与上一次commit保持一致
<pre><code>$ git reset --hard</code></pre>
#####重置当前分支的指针为指定commit，同时重置暂存区，但工作区不变
<pre><code>$ git reset [commit]</code></pre>
#####重置当前分支的HEAD为指定commit，同时重置暂存区和工作区，与指定commit一致
<pre><code>$ git reset --hard [commit]</code></pre>
#####重置当前HEAD为指定commit，但保持暂存区和工作区不变
<pre><code>$ git reset --keep [commit]</code></pre>
#####新建一个commit，用来撤销指定commit，后者的所有变化都将被前者抵消，并且应用到当前分支
<pre><code>$ git revert [commit]</code></pre>

*****
git的使用，平日工作也用git，但是用sourcetree比较多，今日特记录一些指令，参照了阮一峰老师博客中的一些内容，感谢，日后会将其他工作中用到的指令在详细添加到以上的内容中。
