# 命令

这里主要介绍一下 GitBook 的命令行工具 gitbook-cli 的一些命令, 首先说明两点:

* `gitbook-cli` 和 `gitbook` 是两个软件
* `gitbook-cli` 会将下载的 `gitbook` 的不同版本放到 `~/.gitbook`中, 可以通过设置`GITBOOK_DIR`环境变量来指定另外的文件夹

## 列出gitbook所有的命令
```
gitbook help
```

## 输出gitbook-cli的帮助信息
```
gitbook --help
```

## 初始化一个目录
新建目录列表文件：SUMMARY.md  和 README.md 文件，使用以下命令会根据 目录列表生成目录结构和空文件
```vim
SUMMARY.md

This is the summary of my book.

* [section 1](section1/README.md)
    * [example 1](section1/example1.md)
    * [example 2](section1/example2.md)
* [section 2](section2/README.md)
    * [example 1](section2/example1.md)

$ gitbook init
```

## 生成静态网页
```
gitbook build
```

## 生成静态网页并运行服务器
实时预览

```
gitbook serve
```

## 生成时指定gitbook的版本, 本地没有会先下载
高版本的会生成基于服务器版本的静态文件，单独打开里面的链接不能跳转，报错：ajax跨域
```
gitbook build --gitbook=2.0.1
```

## 列出本地所有的gitbook版本
```
gitbook ls
```

## 列出远程可用的gitbook版本
```
gitbook ls-remote
```

## 安装对应的gitbook版本
```
gitbook fetch 标签/版本号
```

## 更新到gitbook的最新版本
```
gitbook update
```

## 卸载对应的gitbook版本
```
gitbook uninstall 2.0.1
```

## 指定log的级别
```
gitbook build --log=debug
```

## 输出错误信息
```
gitbook builid --debug
```

## 配置完成后需要安装到目录
```
gitbook install ./
```

## 生成电子书

> 参考目录：https://toolchain.gitbook.com/ebook.html

在新版本的gitbook中不需要安装其他node客户端，运行`gitbook pdf ./ ./mybook.pdf`，前提是要安装对应系统的 `calibre-3.7.0.msi`