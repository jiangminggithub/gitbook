# 安装介绍



这一章主要介绍本地 `Gitbook` 相关环境的安装，目前主流的平台：Windows、Linux、Unix，Mac OS都是支持的。本地安装需要依赖 `Node.js` 环境 ，如果需要输出 PDF， eBook，Mobi 等格式的电子书还需要安装 `ebook-concert` 依赖，好了，下面进入正题！



# 环境准备



### 下载和安装 Node.js

- 官网：[https://nodejs.org/](https://nodejs.org)
- 官网（中文）：[https://nodejs.org/zh-cn](https://nodejs.org/zh-cn)
- 中文镜像网站：[http://nodejs.cn](http://nodejs.cn)
- 淘宝的镜像下载：[https://npm.taobao.org/mirrors/node](https://npm.taobao.org/mirrors/node)



进入上面网站进入选择相关平台下载对应的版本的 Node.js 方法或者安装包，一种是官网根据不同的平台对应的命令来安装，还有一种是下载二进制安装包（笔者推荐方法），进行环境变量配置，本文将介绍笔者的环境安装 Node.js，笔者使用的是**`Linux Ubuntu`**环境，使用二进制安装包来安装。

> 注意:  基于截止到目前的 Gitbook V3.2.3版本，需要使用NodeJs的v10+版本，否则会产生各种报错。
> 推荐使用：[node-v10.24.0-linux-x64](https://npm.taobao.org/mirrors/node/v10.24.0/)



下载 node-v10.24.0-linux-x64 版本的压缩包后，解压到特定的目录，进行环境变量配置。

```bash
执行 vim ~/.profile 或者 vim ~/.bashrc 后添加下面的环境变量配置

$ vim ~/.profile
export DART_HOME=TargetPath/node-v10.24.0-linux-x64
export PATH=${DART_HOME}/bin:$PATH
```


安装完成之后，可以通过下面的命令来验证一下 `Node.js` 是否安装成功。

```bash
$ node -v                                                
v10.24.0
```



### 安装 ebook-concert 依赖

`ebook-concert` 主要用于生成 PDF、eBook，Mobi 等格式的电子书，具体各平台的下载安装参考官网：[https://calibre-ebook.com/download](https://calibre-ebook.com/download)

这里我是使用的Ubuntu平台，执行下面的命令即可：

```bash
sudo -v && wget -nv -O- https://download.calibre-ebook.com/linux-installer.sh | sudo sh /dev/stdin
```



安装完成之后，可以通过下面的命令来验证一下 `ebook-concert` 是否安装成功。

```bash
$ ebook-convert --version
ebook-convert (calibre 5.13.0)
Created by: Kovid Goyal <kovid@kovidgoyal.net>
```



# 安装 gitbook-cli

执行安装命令, 可参考：[https://www.npmjs.com/package/gitbook](https://www.npmjs.com/package/gitbook)

```bash
$ npm config set registry http://registry.npm.taobao.org   // 可选，设置一下淘宝镜像
$ npm install gitbook-cli -g
```



安装完成之后，可以通过下面的命令来验证一下 `Gitbook` 是否安装成功。

```bash
$ gitbook -V
CLI version: 2.3.2
GitBook version: 3.2.3
```



**看到正确的输出版本信息，到此就完成了 `Ubuntu` 平台的 `Gitbook` 的安装了。**

