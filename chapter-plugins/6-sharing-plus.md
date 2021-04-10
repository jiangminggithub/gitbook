# sharing-plus 分享当前页面



分享当前页面的插件，比默认的 `sharing` 插件多了一些分享方式，同样可以通过配置插件属性进行相关的配置，可以通过实际需要进行相关配置。

**配置使用方法：**

```json
{
    "plugins": ["-sharing", "sharing-plus"],
    "pluginsConfig": {
        "sharing": {
            "douban": false,
            "facebook": true,
            "google": false,
            "hatenaBookmark": false,
            "instapaper": false,
            "line": false,
            "linkedin": true,
            "messenger": false,
            "pocket": true,
            "qq": false,
            "qzone": false,
            "stumbleupon": false,
            "twitter": true,
            "viber": false,
            "vk": false,
            "weibo": false,
            "whatsapp": false,
            "all": [
                "facebook", "google", "twitter",
                "weibo", "instapaper", "linkedin",
                "pocket", "stumbleupon"
            ]
        }
    }
}
```

插件参考地址：[https://www.npmjs.com/package/gitbook-plugin-sharing-plus](https://www.npmjs.com/package/gitbook-plugin-sharing-plus)



**效果预览：**参考本书的右上角 `分享` 图标













<!-- ex_nonav -->
<!-- ex_nolevel -->