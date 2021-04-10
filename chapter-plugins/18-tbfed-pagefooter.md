# tbfed-pagefooter 添加页脚和版权



可以添加`页脚，版权信息`。

**配置使用方法：**

```json
{
    "plugins": [
       "tbfed-pagefooter"
    ],
    "pluginsConfig": {
        "tbfed-pagefooter": {
            "copyright":"Copyright ©JiangMing",
            "modify_label": "更新时间：",
            "modify_format": "YYYY-MM-DD HH:mm:ss"
        }
    }
}
```


如果想自定义一个链接说明，自己可以去index.js里，把 `powered by gitbook`，改成
`powered by <a href="你的说明内容链接" target="_blank">`你的说明内容</a>

插件 Github 地址：[https://github.com/zhj3618/gitbook-plugin-tbfed-pagefooter](https://github.com/zhj3618/gitbook-plugin-tbfed-pagefooter)



**效果预览，参考本页尾的【页脚和版权】效果。**













<!-- ex_nonav -->
<!-- ex_nolevel -->