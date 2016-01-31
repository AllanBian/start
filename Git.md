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





