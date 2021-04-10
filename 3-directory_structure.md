# 简单介绍
本章来介绍一下 `Gitbook` 的目录结构，下面的目录结构表示了一个简单的 Gitbook 的目录结构。

```bash
.
├── book.json
├── README.md
├── SUMMARY.md
├── GLOSSARY.md
├── chapter-1/
|   ├── README.md
|   └── something.md
└── chapter-2/
    ├── README.md
    └── something.md
```

**GitBook 目录文件的主要功能：**

| 文件名      | 描述                      |
| :---------- | :------------------------ |
| book.json   | 配置数据 (可选)           |
| README.md   | 电子书的前言或简介 (必需) |
| SUMMARY.md  | 电子书目录 (可选)         |
| GLOSSARY.md | 词汇/注释术语列表 (可选)  |



# 菜单结构

`SUMMARY.md` 文件描述了书籍的菜单结构。
1. `[]` 指定菜单项目的标题
2. `()` 指定菜单文章文件的路径
3. 支持子目录的方式，章节和子章节用`两个`、`四个空格`或者`tab`键来分级
4. `#` 或者 `---` 进行不同 `Part`  的分类，分别由标题或者水平分割线方式表示不同的部分
5. 区域导航定位，在章节 `路径 md` 文件结尾使用 `#` 号加上文章内容中章节的标题就能实现区域导航

```
# Summary

### Part I
* [Part I](part1/README.md)
    * [Writing is nice](part1/README.md#writing)
    * [GitBook is nice](part1/README.md#gitbook)

### Part II
* [Part II](part2/README.md)
    * [We love feedback](part2/README.md#feedback)
    * [Better tools for authors](part2/README.md#tools)

----
* [Last part without title](part3/title.md)
```



# 页面文件

`Gitbook` 书籍的页面文件采用 `Markdown` 的语法实现，电子书的第一页内容是从文件 `README.md` 中提取的。如果这个文件名没有出现在 `SUMMARY` 中，那么它会被添加为章节的第一个条目。对 Markdown 语法不熟悉的可以参考：[菜鸟教程](https://www.runoob.com/markdown/md-tutorial.html)、[MarkDown中文网](http://markdown.p2hp.com/index.html) 或者其他参考的网站。


**参考示例：**

```
# Title of the chapter

This is a great introduction.

## Section 1

Markdown will dictates _most_ of your **book's structure**

## Section 2

...

```

**页面顶部描述**

它使用 YAML 格式的风格来定义文档的描述信息，在`三条虚线之间`，文档中也可以不写顶部描述，这个不是必须的。

**参考示例：**

```
---
description: This is a short description of my page
---

# The content of my page
...
```



# 专业术语列表

在 Gitbook 中使用 `GLOSSARY.md`  来进行`专业术语列表的配置`。将一些专业名词，名词或者术语的解释配置定义在文件中，在书籍中使用到对应专业术语的地方就可以链接到专业解释的地方。

定义的方式是在 GLOSSARY.md 使用 `##` 列表来定义专业术语的列表。

参考示例：

```
## markdown
Markdown是一种轻量级标记语言，创始人为约翰·格鲁伯（英语：John Gruber）。 
它允许人们使用易读易写的纯文本格式编写文档，然后转换成有效的XHTML（或者HTML）文档。
这种语言吸收了很多在电子邮件中已有的纯文本标记的特性。

## gitbook
GitBook 是一个基于 Node.js 的命令行工具，可使用 Github/Git 和 Markdown 来制作精美的电子书。

## Term
Definition for this term

## Another term
With it's definition, this can contain bold text
and all other kinds of inline markup ...
```



# 忽略文件

在 `SUMMARY.md` 中未列出的文件。所有静态文件，包含图片、JS、CSS都会复制到对应目录下，对于一些不需要的文件，GitBook将读取 `.gitignore`、`.bookignore` 和 `.ignore` 文件，以获取要忽略的文件和文件夹的列表。被忽略的文件不会被上传到版本中。这些文件的语法和 `Git` 中的 gitignore 语法相同。

**参考示例：**

```
# This is a comment

# Ignore the file test.md
test.md

# Ignore everything in the directory "bin"
bin/*
```



# 以子目录的方式与项目集成

对于 Gitbook 书籍项目，可以使用`子目录`(如example-docs/)来存储项目的文档。您可以在 `book.json` 中通过配置选项告诉 `GitBook` 在那里找到根目录
> 注意：`book.json` 文件除外， book.json 文件所在位置代表的就是项目的根目录，但是可以将书籍项目的其他文件放置在子目录。

**参考示例：**

```
1. 项目目录结构：
.
├── book.json
└── example-docs/
    ├── README.md
    └── SUMMARY.md

2. book.json 中的配置：
{
    "root": "./example-docs"
}
```



# 总结

本章介绍了 `Gitbook` 中的基本目录的结构和对应的用处。熟悉后可以对 Gitbook 的体系结构更加熟悉，同时也能更好的去书写你的书籍了。

**参考：**[官网介绍](https://github.com/GitbookIO/gitbook/blob/master/docs/structure.md)
