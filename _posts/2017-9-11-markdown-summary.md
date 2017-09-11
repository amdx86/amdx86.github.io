---
layout: post
title: Markdown Style Guide
---

正文例子 This is a demo of all styled elements in Jekyll Now.

超链接例子如下
[View the markdown used to create this post](https://raw.githubusercontent.com/barryclark/www.jekyllnow.com/gh-pages/_posts/2014-6-19-Markdown-Style-Guide.md).

This is a paragraph, it's surrounded by whitespace. Next up are some headers, they're heavily influenced by GitHub's markdown style.

H1 默认被占用了
第一种：通过在文字下方添加“=”和“-”，他们分别表示一级标题和二级标题。
第二种：在文字开头加上 “#”，通过“#”数量表示几级标题。一共只有1~6级标题，1级标题字体最大
## Header 2 (H1 is reserved for post titles)##

### Header 3

#### Header 4

A link to [Jekyll Now](http://github.com/barryclark/jekyll-now/). A big ass literal link <http://github.com/barryclark/jekyll-now/>

An image, located within /images

![an image alt text]({{ site.baseurl }}/images/jekyll-logo.png "an image title")

在文字开头添加(*, +, and -)实现无序列表。但是要注意在(*, +, and -)和文字之间需要添加空格
* A bulletted list
- alternative syntax 1
+ alternative syntax 2
  - an indented list item


使用数字后面跟上句号。（还要有空格）
1. An
2. ordered
3. list

Inline markup styles:
用两个\_夹起来的是斜体
用两个\*或者两个\\__夹起来的是斜体
 
- _italics_
- **bold**
- `code()`

块注释>，多级嵌套是>>
> Blockquote
>> Nested Blockquote

Syntax highlighting can be used with triple backticks, like so:

```javascript
/* Some pointless Javascript */
var rawr = ["r", "a", "w", "r"];
```

Use two trailing spaces  
on the right  
to create linebreak tags  

Finally, horizontal lines

----
****
