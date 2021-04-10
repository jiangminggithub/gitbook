# 导出电子书



**目前为止，Gitbook 支持如下输出：**

- 静态HTML（静态网站）
- PDF格式
- eBook格式
- Mobi 格式



>  [!TIP|style:flat]
>
> 目前常见的电子书格式主要主要有三种(`ePub`, `Mobi`, `PDF`)，在 `Gitbook` 中导出这三种格式都依赖于系统本身提供的 `ebook-convert` 工具支持.



在本书的`安装章节中`已经介绍了怎么安装 `ebook-convert` 工具，再这里就不多介绍了，接下来将针对上面的几种常见的电子书的导出进行介绍。



# 基本命令



> [!Note|style:flat]
>
> 语法格式: 
>
> - gitbook build：导出静态网站HTML格式文件
>
> - gitbook pdf：导出PDF格式文件
>
> - gitbook epub：导出ePub格式文件
>
> - gitbook mobi：导出Mobi格式文件



简单示例：

```bash
# 1. 生成 `html` 静态网站文件并输出 `debug` 级别日志
$ gitbook build --log=debug

# 2. 生成 `pdf` 文件并输出 `debug` 级别日志
$ gitbook pdf book.pdf --log=debug

# 3. 生成 `epub` 文件并输出 `debug` 级别日志
$ gitbook epub book.epub --log=debug

# 4. 生成 `mobi` 文件并输出 `debug` 级别日志
$ gitbook mobi book.mobi --log=debug
```



<!-- ex_nonav -->
<!-- ex_nolevel -->
