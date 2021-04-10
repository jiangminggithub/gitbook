# flexible-alerts 高级格式显示的提示块



这个插件将块引用转换为漂亮的警报。可以在全局和警报特定级别配置外观，因此输出确实符合您的需求。此外，您还可以提供自己的警报类型（比如最后的comment）。


**配置使用方法：**


```json
{
    "plugins": [
      "flexible-alerts"
    ],
    "pluginsConfig": {
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

**用法：**
```markdown
> [!type|style:xx|label:xx|icon:xx|className:xx|labelVisibility:xx|iconVisibility:xx]
> 内容部分
```

字段介绍，如果不设置的表示选择默认，除了!type都不是必需的。


| 键              | 允许的值                            | 说明                                               |
| :-------------- | :---------------------------------- | :------------------------------------------------- |
| !type           | NOTE，TIP，WARNING和DANGER          | 警告级别设置                                       |
| style           | 以下值之一: callout（默认）, flat   | 警告样式，见图19的左右不同                         |
| label           | 任何文字                            | 警告块的标题位置，即Note这个字段位置（不支持中文） |
| icon            | e.g. 'fa fa-info-circle'            | 一个有效的Font Awesome图标，那块小符号             |
| className       | CSS类的名称                         | 指定css文件，用于指定外观                          |
| labelVisibility | 以下值之一：visible（默认），hidden | 标签是否可见                                       |
| iconVisibility  | 以下值之一：visible（默认），hidden | 图标是否可见                                       |


```markdown
1. 这是简单的用法
> [!NOTE]
> 这是一个简单的Note类型的使用，所有的属性都是默认值。

---
2. 这是自定义属性的用法
> [!NOTE|style:flat|lable:Mylable|iconVisibility:hidden]
> "!type":`NOTE`、"style":`flat`、"lable":`自定义标签`、图标不可见
```
`json` 配置个性化，自定义一个COMMENT类型使用。

```json
"pluginsConfig": {
      "flexible-alerts": {
        "style": "callout",
        "comment": {
          "label": "Comment",
          "icon": "fa fa-comments",
          "className": "info"
        }
      }
    }
```

**使用：**

```json
> [!COMMENT]
> An alert of type 'comment' using style 'callout' with default settings.
```

插件 Github 地址：[https://github.com/fzankl/gitbook-plugin-flexible-alerts](https://github.com/fzankl/gitbook-plugin-flexible-alerts)



**效果预览：**

1. 简单的使用效果：

Note:
> [!NOTE]
> 这是一个简单的Note类型的使用，所有的属性都是默认值。

TIP:
> [!TIP]
> 这是一个简单的Note类型的使用，所有的属性都是默认值。


WARNING:
> [!WARNING]
> 这是一个简单的Note类型的使用，所有的属性都是默认值。

DANGER:
> [!DANGER]
> 这是一个简单的Note类型的使用，所有的属性都是默认值。



2. 自定义属性效果：
> [!NOTE|style:flat|lable:Mylable|iconVisibility:hidden]
> "!type":`NOTE`、"style":`flat`、"lable":`自定义标签`、图标不可见



3. 个性化使用效果：

   > [!COMMENT]
   > An alert of type 'comment' using style 'callout' with default settings.









<!-- ex_nonav -->
<!-- ex_nolevel -->