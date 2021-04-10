# lightbox 点击图片弹窗显示



这个插件可以单击图片，以图片`本身大小的方式弹窗显示`图片和一些图片相关的 `Alt` 的信息。

**配置使用方法：**

```json
{
    "plugins": [
        "lightbox"
    ],
    "lightbox": {
        "includeJQuery": false,
        "sameUuid": true,
        "options": {
            "resizeDuration": 500,
            "wrapAround": false
        }
    }
}
```
配置参数介绍：

- `includeJQuery`: 如果你的项目中已经引入了 `JQuery` 可以在此设置是否包含插件本身的 JQuery。
- `sameUuid`：在图片预览中添加上一个、下一个按钮来浏览本页面的图片配置。
- `options`： 这个选项配置显示的动画时长，是否包裹等相关配置。


插件 Github 地址：[https://github.com/vongola12324/gitbook-plugin-lightbox](https://github.com/vongola12324/gitbook-plugin-lightbox)




**效果预览：**



![logo-jim-bg 点击查看图片](../images/icon/logo-jim-bg.png "点击查看图片")









<!-- ex_nonav -->
<!-- ex_nolevel -->