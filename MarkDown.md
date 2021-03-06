#Markdown用法说明

###标题
#####setext形式:利用=(最高标题)和-(第二阶标题)
示例如下:
最高标题
===========
第二阶标题
-----------
代码如下:
<pre>
	<code>
最高标题
===========
第二阶标题
-----------
	</code>
</pre>
*****
#####atx形式:在行首插入1-6个#来表示
示例如下:
#标题1
#####标题5
代码如下:
<pre>
	<code>
#标题1
#####标题5	
	</code>
</pre>
*****


###区块引用
#####行首使用>来表示区块，在区块中可以使用其他markdown语法
示例如下:

> 这是一个区块
>
>> 又是一个区块 
>
> 这里还是一个区块

代码如下:
<pre>
	<code>
&gt; 这是一个区块
&gt;
&gt;&gt; 又是一个区块
&gt;
&gt; 这里还是一个区块
	</code>
</pre>
*****

###列表
#####无序列表，可以使用星号，加号，或是减号作为列表标记
示例如下:

* 红
* 黄
* 蓝
+ R
+ G
+ B
- 上
- 中
- 下

代码如下:
<pre><code>
* 红
* 黄
* 蓝
+ R
+ G
+ B
- 上
- 中
- 下	
</code></pre>
*****
#####有序列表，可以使用数字加英文的.作为标记
示例如下:

1. 红
2. 黄
3. 蓝

代码如下:
<pre><code>
1. 红
2. 黄
3. 蓝	
</code></pre>
*****

###调整缩进
#####利用空格调整缩进，在文字中添加至少一个空格或制表符即可。
示例如下:

*	这是一段有缩进的文字。   
	这是一段有缩进的文字。   
	这是一段有缩进的文字。   

代码如下:
<pre><code>
*	这是一段有缩进的文字，这段文字最后有2个空格。   
	这是一段有缩进的文字，这段文字最后有2个空格。   
	这是一段有缩进的文字，这段文字最后有2个空格。   	
</code></pre>
*****

###代码区块
#####使用pre和code标签将代码包裹起来

示例如下:
<pre><code>
	这里是放置代码的区域
</code></pre>

代码如下:
<pre><code>
	&lt;pre&gt;
		&lt;code&gt;
			这里是放置代码的区域
		&lt;/code&gt;
	&lt;/pre&gt;
</code></pre>
*****

###分割线
#####使用3个以上的星号，减号，底线来建立一个分割线，行内不能有其他东西，可以在星号或者减号中间插入空格


示例如下:  
***
---

代码如下:
<pre><code>
---
***	
</code></pre>
*****

###区段元素
#####行内式链接
只要在方括号后面紧接圆括号并插入网址链接即可，如果要加title，只要在网址后面用双引号把title文字包起来即可

示例如下:

This is [github](https://github.com "github") link.

代码如下:
<pre><code>
<p>This is [github](https://github.com "github") link.</p>
</code></pre>

#####参考式链接
在链接文字的方括号后面接上一个方括号作为标记，然后在文件任意处定义标记的链接内容，可以在最后面用单引号、双引号或括号来定义标题


示例如下:

This is [github][g_link] link.
[g_link]: https://github.com "github"

代码如下:
<pre><code>
<p>This is [github][g_link] link.</p>
<p>[g_link]: https://github.com "github"</p>
</code></pre>

#####隐式链接标记
让你可以省略指定链接标记,这种情况下会视为等同于链接文字，要用隐式链接标记只要在链接文字后面加一个空的方括号

示例如下:

[github][]
[github]:https://github.com

代码如下:
<pre><code>
<p>[github][]</p>
<p>[github]:https://github.com</p>
</code></pre>
*****

###强调
#####使用星号和底线作为标记强调字词打符号，被一个包围会转成\<em\>，两个包围会转成\<strong\>,如果两边都有空格它们只会被当成普通符号。

示例如下:

*强调*
_强调_
**强调**
__强调__

代码如下:
<pre><code>
*强调*
_强调_
**强调**
__强调__	
</code></pre>
*****

###代码
#####如果要标记一小段行内代码，可以用反引号把它包起来 \` 

示例如下:

使用 `fun()` 方法

代码如下:

<pre><code>
使用 `fun()` 方法	
</code></pre>
*****

#####如果要在代码区段内插入反引号，可以用多个反引号来开启和结束代码区段

示例如下:

看看会发生什么``测试一下多个反引号(`)。``看看会发生什么

看看会发生什么<code>测试一下多个反引号(`)。</code>看看会发生什么


代码如下:
<pre><code>
看看会发生什么``测试一下多个反引号(`)。``看看会发生什么

看看会发生什么&lt;code&gt;测试一下多个反引号(`)。&lt;/code&gt;看看会发生什么
</code></pre>
*****

#####代码区段的起始和结束端都可以放入一个空白，起始端后面一个，结束端前面一个，这样就可以在区段的一开始就插入反引号了

示例如下:

让我们来`` `测试一下` ``咯!

让我们来<code>\`测试一下\`</code>咯!

代码如下:
<pre><code>
让我们来`` `测试一下` ``咯!

让我们来&lt;code&gt;\`测试一下\`&lt;/code&gt;咯!
</code></pre>
*****

###图片
#####链接图片的语法同样允许两种样式:行内式和参考式(主要的区别是开头有个感叹号)

示例如下:
![AllanBian](https://avatars2.githubusercontent.com/u/973357?v=3&s=460 "AllanBian")
![allan's photo][photo]
[photo]:https://avatars2.githubusercontent.com/u/973357?v=3&s=40 "allan's photo"

代码如下:
<pre><code>
<p>![AllanBian](https://avatars2.githubusercontent.com/u/973357?v=3&s=460 "AllanBian")	</p>
<p>![allan's photo][photo]</p>
<p>[photo]:https://avatars2.githubusercontent.com/u/973357?v=3&s=40 "allan's photo"</p>
</code></pre>
*****

###其他
#####自动链接，自动将一般网址转换成链接

示例如下:
<https://github.com>

代码如下:
<pre><code>
<p>&lt;https://github.com&gt;</p>
</code></pre>
*****

#####反斜杠，利用反斜杠插入一些在语法中有其他意义的符号，例如用星号加在文字旁边做强调效果而不是\<em\>标签，可以在星号前面加反斜杠

示例如下:
\\
\`
\*
\_
\{\}
\[\]
\(\)
\#
\+
\-
\.
\!

代码如下:
<pre><code>
\\
\`
\*
\_
\{\}
\[\]
\(\)
\#
\+
\-
\.
\!	
</code></pre>
*****
