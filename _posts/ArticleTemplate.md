---
layout: post
title: ArticleTemplate
author: wingstone
meta: "Springfield"
categories: junk
---

第一段应该为简短的段落头，用来介绍文章的大致内容，这段会显示在博客列表里；

## 段落标题应该为h2

因为h1显示出来的标题实在是太大了。。。
*前面的meta跟categories有啥用，我以后再试==*

### 次级段落标题为h3

这是次段的内容，这个文章用来做实验，因此就不加日期前缀了，不然显示在网页里就暴露了==

## jekyll提供的一些功能
在jekyll制作的网站里，提供了一下liquid tags来嵌套code snippets，比如：
{% highlight ruby %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}

也提供了另外一种的网站链接方式，比如：
[点击这里到我的主页][wingstone-blog-home]

*下面这个怎么用，我也得以后试试*
{% comment %}
Might you have an include in your theme? Why not try it here!
{% include my-themes-great-include.html %}
{% endcomment %}


## 我觉得这些功能可以直接用markdown提供的==
比如嵌套代码：
```c++
float str = "hello world"
```
在比如连接网站：
[点击这里到我的主页](https://wingstone.github.io/)

### Tables

这里放个表格的markdown使用，因为我不常用，这里记一下==

Title 1               | Title 2               | Title 3               | Title 4
--------------------- | --------------------- | --------------------- | ---------------------
lorem                 | lorem ipsum           | lorem ipsum dolor     | lorem ipsum dolor sit
lorem ipsum dolor sit | lorem ipsum dolor sit | lorem ipsum dolor sit | lorem ipsum dolor sit
lorem ipsum dolor sit | lorem ipsum dolor sit | lorem ipsum dolor sit | lorem ipsum dolor sit
lorem ipsum dolor sit | lorem ipsum dolor sit | lorem ipsum dolor sit | lorem ipsum dolor sit


Title 1 | Title 2 | Title 3 | Title 4
--- | --- | --- | ---
lorem | lorem ipsum | lorem ipsum dolor | lorem ipsum dolor sit
lorem ipsum dolor sit amet | lorem ipsum dolor sit amet consectetur | lorem ipsum dolor sit amet | lorem ipsum dolor sit
lorem ipsum dolor | lorem ipsum | lorem | lorem ipsum
lorem ipsum dolor | lorem ipsum dolor sit | lorem ipsum dolor sit amet | lorem ipsum dolor sit amet consectetur



[wingstone-blog-home]: https://wingstone.github.io/