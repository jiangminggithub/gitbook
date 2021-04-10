# Gitbook命令行的使用



 `Gitbook` 的命令行工具其实就是 `gitbook-cli` ，可以通过命令的方式来创建，构造，安装插件，预览等功能。



# 查看帮助



`Gitbook` 和 `Git` 一样是一个命令行工具，开始介绍之前，先使用 `gitbook help` 命令来概览看一下 gitbook 主要的几个命令。

```bash
$ gitbook help
build [book] [output]       build a book
   --log                   Minimum log level to display (Default is info; Values are debug, info, warn, error, disabled)
   --format                Format to build to (Default is website; Values are website, json, ebook)
   --[no-]timing           Print timing debug information (Default is false)

serve [book] [output]       serve the book as a website for testing
   --port                  Port for server to listen on (Default is 4000)
   --lrport                Port for livereload server to listen on (Default is 35729)
   --[no-]watch            Enable file watcher and live reloading (Default is true)
   --[no-]live             Enable live reloading (Default is true)
   --[no-]open             Enable opening book in browser (Default is false)
   --browser               Specify browser for opening book (Default is )
   --log                   Minimum log level to display (Default is info; Values are debug, info, warn, error, disabled)
   --format                Format to build to (Default is website; Values are website, json, ebook)

install [book]              install all plugins dependencies
   --log                   Minimum log level to display (Default is info; Values are debug, info, warn, error, disabled)

parse [book]                parse and print debug information about a book
   --log                   Minimum log level to display (Default is info; Values are debug, info, warn, error, disabled)

init [book]                 setup and create files for chapters
   --log                   Minimum log level to display (Default is info; Values are debug, info, warn, error, disabled)

pdf [book] [output]         build a book into an ebook file
   --log                   Minimum log level to display (Default is info; Values are debug, info, warn, error, disabled)

epub [book] [output]        build a book into an ebook file
   --log                   Minimum log level to display (Default is info; Values are debug, info, warn, error, disabled)

mobi [book] [output]        build a book into an ebook file
   --log                   Minimum log level to display (Default is info; Values are debug, info, warn, error, disabled)
```



> [!WARNING|style:flat]
>
> - 其中```[]```标记的是 ** 可选参数 **指令，但是有可能在某些平台中不生效甚至会报错。可能是 gitbook 在平台的兼容性上还不够完善原因导致的，如有参数使用的需求的情况，可以根据需要选择适合的平台来使用。目前笔者测试过在部分 `Ubuntu` 环境平台上部分参数指令可能无效（可能简写命令格式支持，或许支持完整参数格式又或许都不支持），但是在 `Windows` (windows 10) 平台上是可以使用的，具体的参数是否可正常的使用取决于不同平台的支持程度。
>
> - `--` 标记的是可选的功能参数，如 --log 输出执行相关的log，具体功能描述参考上面help中后面的描述。



**简单的了解一下这些参数吧：**

- [book]：指定 `gitbook` 项目的目录
- [output]：指定文件输出的目录



**使用示例：**

```bash
# 在指定的/home/gitbook/目录中初始化一个书籍项目
$ gitbook init --book=/home/gitbook/
# 对应的简写格式
$ gitbook init /home/gitbook/

# 指定书籍项目目录在当前目录，并将编译构建后文件放到指定的当前目录下的mybook目录中
$ gitbook build --book=./  --output=./mybook
# 对应的简写格式
$ gitbook build ./ ./mybook

# 指定书籍项目目录在当前目录，导出 PDF 格式的电子书到指定的/home/pdf/目录中
$ gitbook pdf --book=./  --output=/home/pdf/
# 对应的简写格式
$ gitbook pdf ./ /home/pdf/
```



# 初始化



使用 `gitbook init` 初始化一本书，本地会默认创建生成两个 `markdown` 格式的文件，这两个文件是必须存在的，一个是初始化页面，一个是电子书的目录结构定义文件。

```bash
# 电子书初始化
$ gitbook init  
warn: no summary file in this book 
info: create README.md 
info: create SUMMARY.md 
info: initialization is finished 

# 查看初始化的目录结构
$ tree
.
├── README.md
└── SUMMARY.md
```



# 构建电子书



使用 `git build` 命令来生成静态网页格式的电子书。执行后会生成HTML静态资源输出到当前项目的目录下`_book` 目录中。

```bash
# 构建电子书
$ gitbook build
info: 21 plugins are installed 
info: 18 explicitly listed 
info: loading plugin "highlight"... OK 
info: loading plugin "chapter-fold"... OK 
info: loading plugin "anchor-navigation-expand"... OK 
info: loading plugin "search-pro"... OK 
info: loading plugin "code"... OK 
info: loading plugin "splitter"... OK 
info: loading plugin "sharing-plus"... OK 
info: loading plugin "advanced-emoji"... OK 
info: loading plugin "github"... OK 
info: loading plugin "alerts"... OK 
info: loading plugin "auto-scroll-table"... OK 
info: loading plugin "popup"... OK 
info: loading plugin "hide-element"... OK 
info: loading plugin "donate"... OK 
info: loading plugin "tbfed-pagefooter"... OK 
info: loading plugin "fontsettings"... OK 
info: loading plugin "theme-default"... OK 
info: found 3 pages 
info: found 0 asset files 
warn: "options" property is deprecated, use config.get(key) instead 
info: >> generation finished with success in 0.7s ! 

# 查看简单的目录结构
$ tree -L 3
.
├── _book
│   ├── gitbook
│   │   ├── fonts
│   │   ├── gitbook.js
│   │   ├── gitbook-plugin-fontsettings
│   │   ├── gitbook-plugin-highlight
│   │   ├── gitbook-plugin-lunr
│   │   ├── gitbook-plugin-search
│   │   ├── gitbook-plugin-sharing
│   │   ├── images
│   │   ├── style.css
│   │   └── theme.js
│   ├── index.html
│   └── search_index.json
├── README.md
└── SUMMARY.md
```



# 安装插件



在书籍的配置文件（后续有配置相关文章）配置好需要的 Gitbook 插件，执行 `gitbook install` 就可以在线安装相关插件了。

```bash
$ gitbook install
info: installing 15 plugins using npm@3.9.2 
info:  
info: installing plugin "highlight"
......
```



出现这样的输出后，就等待插件安装完成就可以使用了，如果插件配置错误，会中途直接报错停止，需要解决错误后才可以继续安装。



# 本地静态电子书预览



使用 `gitboo serve` 命令开启进行本地网页预览服务，执行后会默认执行 `gitbook build` 命令，然后本地开启一个端口 `4000` 的预览网页服务，此时可以通过浏览器访问本地机器 4000 端口进行电子书的浏览。

```bash
$ gitbook serve
Live reload server started on port: 35729
Press CTRL+C to quit ...

info: 21 plugins are installed 
info: 19 explicitly listed 
info: loading plugin "highlight"... OK 
info: loading plugin "chapter-fold"... OK 
info: loading plugin "anchor-navigation-expand"... OK 
info: loading plugin "search-pro"... OK 
info: loading plugin "code"... OK 
info: loading plugin "splitter"... OK 
info: loading plugin "sharing-plus"... OK 
info: loading plugin "advanced-emoji"... OK 
info: loading plugin "github"... OK 
info: loading plugin "alerts"... OK 
info: loading plugin "auto-scroll-table"... OK 
info: loading plugin "popup"... OK 
info: loading plugin "hide-element"... OK 
info: loading plugin "donate"... OK 
info: loading plugin "tbfed-pagefooter"... OK 
info: loading plugin "livereload"... OK 
info: loading plugin "fontsettings"... OK 
info: loading plugin "theme-default"... OK 
info: found 3 pages 
info: found 0 asset files 
warn: "options" property is deprecated, use config.get(key) instead 
info: >> generation finished with success in 0.7s ! 

Starting server ...
Serving book on http://localhost:4000
```



**此时通过浏览器打开 `http://localhost:4000` 即可预览静态网页电子书。**

预览效果：

![静态网页电子书预览 预览效果图](./images/Readme.png "预览效果图")



**好了，这就是 `Gitbook` 的主要的几个主要命令，如果需要了解更多，请参考相关网站。**