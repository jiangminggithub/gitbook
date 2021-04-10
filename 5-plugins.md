# 介绍

本章主要来详细的介绍一下 `Gitbook` 中的 **插件** 相关的配置和使用。在 Gitbook 中可以在书籍的配置文件 `book.json` 中来进行插件的相关配置。比如有很多好用的插件，可以很好的拓展书籍的外观，可用性或者其他方便的使用，所以接下来就一起来看看 Gitbook 中插件的使用吧。

配置的方法是在配置文件的 `plugins` 中添加需要的插件名称即可。

如下所示：

```json
"plugins": [
    "search",
    "highlight",
    "sharing",
    "font-settings",
    "livereload",
    ...
]
```



# 默认插件 

Gitbook 中默认带有 5 个插件：


| 名称 | 说明 |
| :--- | :---|
| `highlight` | 语法高亮插件，代码高亮功能 |
| `search` | 搜索插件，不支持中文搜索 |
| `sharing` | 分享插件，右上角分享功能 |
| `font-settings` | 字体设置（最上方的"A"符号） |
| `livereload` | 热加载插件，为 GitBook 编辑进行实时重新预览加载 |



# 禁用自带的插件
如果需要`去除`或者`禁用` Gitbook 中的某个插件，可以在插件名称前面加 `-` 。

如下所示：

```json
"plugins": [
    "-search",
    "-highlight",
    "-sharing",
    "-font-settings",
    "-livereload",
    ...
]
```



# 添加插件列表

如果需要添加一些**第三方的自定义插件**，可以在 `plugins` 中添加需要的插件名称列表。

> [!WARNING]
>
> - 有的第三方的插件可能和默认的插件有重复，或者替代默认插件的，需要禁用对应的默认插件，具体用法一般参考对应插件的使用说明。
> - 第三方插件使用的话，可能会破坏书籍的结构，所以使用上需要注意！

例如：

```json
"plugins": [
        "-search",
        "advanced-emoji",
        "search-pro",
        "github",
        "splitter",
        "anchor-navigation-ex",
        "chapter-fold",
        "expandable-chapters-small",
        "code",
        "alerts",
        "insert-logo",
        "flexible-alerts",
        ...
    ]
```



# 插件属性配置 pluginsConfig

配置`插件的属性`在书籍配置文件中的 pluginsConfig 中进行相关插件的属性配置。

例如：配置`insert-logo` 插件的相关属性

 ```json
"pluginsConfig": {
        "insert-logo": {
            "url": "jim-logo.png",
            "style": "background: none; max-height: 100px; min-height: 30px"
        }
    }
 ```


# 总结

到此将插件的配置和使用详细的介绍完了，也列举了一些常用的一些第三方的插件的使用方法，相信现在大家可以很好的利用这些比较好用的第三方的插件，去更好的去构建自己的书籍了。
