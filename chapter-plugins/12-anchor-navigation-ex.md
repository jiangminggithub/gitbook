# anchor-navigation-ex 悬浮目录和回到顶部



**插件功能：**

- 给页面H1-H6标题增加锚点效果
- 浮动导航模式
- 页面内顶部导航模式
- 导航标题前的层级图标是否显示，自定义H1-H3的层级图标
- plugins["theme-default"],页面标题层级与官方默认主题的showLevel层级关联
- plugins["theme-default"],插件样式支持官网默认主题的三种样式：White、Sepia、Night
- 在页面中增加`<extoc></extoc>`标签，会在此处生成TOC目录
- 在页面中增加`<!-- ex_nonav -->`标签，不会在该页面生成悬浮导航
- config.printLog=true,打印当前的处理进度，排错很有用
- config.multipleH1=false,去掉丑陋的多余的1. 序号（如过您的书籍遵循一个MD文件只有一个H1标签的话）
- config.showGoTop=true,显示返回顶部按钮 V1.0.11+
- config.float.floatIcon 可以配置浮动导航的悬浮图标样式 V1.0.12+
- 在页面中增加`<!-- ex_nolevel -->`不会在该页面生成层级序号 V1.0.12+



**配置使用方法：**

```json
{
  "plugins": [
       "anchor-navigation-ex"
  ]
}
```
插件 Github 地址：[https://github.com/zq99299/gitbook-plugin-anchor-navigation-ex](https://github.com/zq99299/gitbook-plugin-anchor-navigation-ex)



**效果预览：**













<!-- ex_nonav -->
<!-- ex_nolevel -->