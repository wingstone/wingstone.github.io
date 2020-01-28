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

## shader canvas尝试
<canvas class="glslCanvas" data-fragment="// Author @patriciogv ( patriciogonzalezvivo.com ) - 2015
// Title: Diamond Tiles

#ifdef GL_ES
precision mediump float;
#endif

#define PI 3.14159265358979323846

uniform vec2 u_resolution;
uniform float u_time;

vec2 rotate2D(vec2 _st, float _angle){
    _st -= 0.5;
    _st =  mat2(cos(_angle),-sin(_angle),
      sin(_angle),cos(_angle)) * _st;
    _st += 0.5;
    return _st;
}

vec2 tile(vec2 _st, float _zoom){
    _st *= _zoom;
    return fract(_st);
}

float box(vec2 _st, vec2 _size, float _smoothEdges){
    _size = vec2(0.5)-_size*0.5;
    vec2 aa = vec2(_smoothEdges*0.5);
    vec2 uv = smoothstep(_size,_size+aa,_st);
    uv *= smoothstep(_size,_size+aa,vec2(1.0)-_st);
    return uv.x*uv.y;
}

vec2 offset(vec2 _st, vec2 _offset){
    vec2 uv;

    if(_st.x>0.5){
        uv.x = _st.x - 0.5;
    } else {
        uv.x = _st.x + 0.5;
    }

    if(_st.y>0.5){
        uv.y = _st.y - 0.5;
    } else {
        uv.y = _st.y + 0.5;
    }

    return uv;
}

void main(void){
    vec2 st = gl_FragCoord.xy/u_resolution.xy;
    st.y *= u_resolution.y/u_resolution.x;

    st = tile(st,10.);

    vec2 offsetSt = offset(st,vec2(0.5));

    st = rotate2D(st,PI*0.25);

    vec3 color = vec3( box(offsetSt,vec2(0.95),0.01) - box(st,vec2(0.3),0.01) + 2.*box(st,vec2(0.2),0.01) );

    gl_FragColor = vec4(color,1.0);
}
" width="500" height="500"></canvas>

[wingstone-blog-home]: https://wingstone.github.io/