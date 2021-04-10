# 简述

本章主要介绍一下 `Gitbook` 中的相关配置以及说明。

Gitbook 使用了可选的 `JSON` 格式的配置文件来自定义书籍和文档的配置，这些配置选项通过 Gitbook项目根目录下的 `book.json` 文件来进行配置和指定。如果对 **JSON** 语法不熟悉的读者，可以参考：[https://www.w3school.com.cn/json/json_syntax.asp](https://www.w3school.com.cn/json/json_syntax.asp) 。



# 配置概览

| 变量            | 说明                                                         |
| :-------------- | :----------------------------------------------------------- |
| `root`          | 包含所有图书文件的根文件夹的路径，除了`book.json`            |
| `title`         | 书籍的标题，默认值从README中提取                             |
| `description`   | 您的书籍说明，默认值从自述文件中提取                         |
| `author`        | 作者姓名                                                     |
| `isbn`          | 书籍的国际码ISBN                                             |
| `language`      | [ISO 语言规范](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes)中的语言规范定义，默认值是 `en` |
| `direction`     | 文本的方向，可以是 `rtl` 或 `ltr`，默认值取决于 `language` 的值 |
| `gitbook`       | GitBook的版本，使用SemVer规范并接受诸如 `">=3.0.0"` 的条件   |
| `structure`     | 指定自述，摘要，词汇表等的路径                               |
| `variables`     | 这个选项定义书籍中的变量                                     |
| `links`         | 在左侧导航栏添加指定的链接信息                               |
| `styles`        | 这个选项是用来自定义书本的css的                              |
| `plugins`       | 指定书籍使用的插件列表                                       |
| `pluginsConfig` | 配置指定插件的一些配置信息                                   |



# 配置示例



## 基础配置

`Gitbook` 基础的配置信息，通过下面的这个方式直接配置在 `book.json` 中。

**参考示例：**

```json
{
    "root":".",
    "author":"JiangMing",
    "title":"JiangMing Gitbook",
    "language":"zh-hans",
    "description":"This is gitbook",
    "isbn":"000-0-00-000000-0",
    "direction":"ltr",
    "gitbook":">=3.2.3"
}
```



## structure 结构配置

除了 `root` 变量，你可以通过 `structure` 告诉Gitbook [Readme]，[Summary]，[Glossary]，[Languages]的文件名(而不是使用默认名称，如README.md)。这些文件必须在您的书籍项目的根目录。不接受像 `doc/README.md` 这样的子目录路径。

| 变量                  | 说明                              |
| :-------------------- | :-------------------------------- |
| `structure.readme`    | 自述文件名(默认为“README.md”)     |
| `structure.summary`   | 摘要文件名(默认为“SUMMARY.md”)    |
| `structure.glossary`  | 词汇表文件名(默认为“GLOSSARY.md”) |
| `structure.languages` | 语言文件名(默认为LANGS.md)        |

**参考示例：**

```json
{
    "structure":{
        "readme":"README.md",
        "summary":"SUMMARY.md",
        "glossary":"GLOSSARY.md",
        "languages":"LANGS.md" // 注意默认已经配置，在 gitbook—V3.2.3版本配置会报错, 可忽略
    }
}
```



## variables 变量配置

定义一些书籍中的变量信息，定义在 `book.json` 中的变量可以在 `book` 作用域下被访问，如：`{{ book.blog }}` 双括号语法在 **书籍中** 获取其中的数值。

**参考示例：**

```json
{
    "variables":{
        "blog":"https://blog.csdn.net/ming_97y"
    }
}
```



## links 链接导航

通过 `links` 配置在左侧导航栏添加指定的链接导航，如：添加自己的**博客链接**，**GIthub链接**等等...

**参考示例：**

```json
{
    "links":{
        "sidebar":{
            "Blog":"https://blog.csdn.net/ming_97y",
            "Github":"https://github.com/jiangminggithub"
        }
    }
}
```



## styles 自定义样式

通过 `styles` 配置这个选项用来自定义书本的 `css` 的。

**参考示例：**

```json
{
    "styles": {
        "website": "styles/website.css",
        "ebook": "styles/ebook.css",
        "pdf": "styles/pdf.css",
        "mobi": "styles/mobi.css",
        "epub": "styles/epub.css"
    }
}
```



## pdf 参数配置

PDF输出可以使用book.json中的 `pdf ` 来进行配置：


| 变量 |	说明 |
| :--- | :--- |
| `pdf.pageNumbers`	|将页码添加到每个页面的底部(默认为true) |
| `pdf.fontSize` |	基本字体大小(默认为12) |
| `pdf.fontFamily` |	基本字体系列(默认为Arial) |
| `pdf.paperSize` |	纸张大小，选项为：`"a0"，"a1"，"a2"，"a3"，"a4"，"a5"，"a6"，"b0"，"b1"，"b2"，"b3", "b4"，"b5"，"b6"，"legal"，"letter"，(默认为"a4")` |
| `pdf.margin.top` |	顶部边距(默认为56) |
| `pdf.margin.bottom` | 底边距(默认为56) |
| `pdf.margin.right`	| 右边距(默认为62) |
| `pdf.margin.left` | 左边距(默认为62) |


**参考示例：**

```json
{
    "pdf":{
        "pageNumbers":true,
        "fontFamily":"Arial",
        "fontSize":12,
        "paperSize":"a4",
        "margin":{
            "right":62,
            "left":62,
            "top":56,
            "bottom":56
        }
    }
}
```



## plugins 插件列表

通过 `plugins` 配置可以配置书籍需要的插件列表。

参考示例：

```json
{
    "plugins": [
        "github",
        "splitter",
        ...
    ]
}
```



## pluginsConfig 插件配置

通过 `插件配置` 可以配置插件列表`plugins`中对应插件的一些配置选项信息。

**参考示例：**

```json
{
    "plugins": ["github"],
    "pluginsConfig": {
        "github": {
            "url": "https://github.com"
        }
    }
}
```



# 参考配置示例

**下面的这个是一个简单的 `book.json` 的配置，可供参考。**

```json
{
    "root": ".",
    "author": "JiangMing",
    "title": "JiangMing Gitbook",
    "language": "zh-hans",
    "description": "This is gitbook",
    "isbn": "000-0-00-000000-0",
    "direction": "ltr",
    "gitbook": ">=3.2.3",
    "structure": {
        "readme": "README.md",
        "summary": "SUMMARY.md",
        "glossary": "GLOSSARY.md"
    },
    "variables": {
        "blog": "https://blog.csdn.net/ming_97y"
    },
    "links": {
        "sidebar": {
            "Blog": "https://blog.csdn.net/ming_97y",
            "Github": "https://github.com/jiangminggithub"
        }
    },
    "styles": {
        "website": "styles/website.css",
        "ebook": "styles/ebook.css",
        "pdf": "styles/pdf.css",
        "mobi": "styles/mobi.css",
        "epub": "styles/epub.css"
    },
    "pdf": {
        "pageNumbers": true,
        "fontFamily": "Arial",
        "fontSize": 12,
        "paperSize": "a4",
        "margin": {
            "right": 62,
            "left": 62,
            "top": 56,
            "bottom": 56
        }
    },
    "plugins": [
        "-lunr",
        "-search",
        "advanced-emoji",
        "search-plus",
        "github",
        "splitter",
        "anchor-navigation-ex",
        "chapter-fold",
        "expandable-chapters-small",
        "code",
        "alerts",
        "insert-logo",
        "flexible-alerts"
    ],
    "pluginsConfig": {
        "github": {
            "url": "https://github.com"
        },
        "insert-logo": {
            "url": "jim-logo.png",
            "style": "background: none; max-height: 100px; min-height: 30px"
        },
        "flexible-alerts": {
            "style": "callout",
            "comment": {
                "label": "Comment",
                "icon": "fa fa-comments",
                "className": "info"
            }
        }
    }
}
```



# 总结

到此就完成了 `Gitbook` 中关于配置文件的相关介绍，了解玩这些配置，就可以更好的去配置和使用 Gitbook 来完成自己的电子书籍的书写了。


**参考：** [官网说明](https://github.com/GitbookIO/gitbook/blob/master/docs/config.md)