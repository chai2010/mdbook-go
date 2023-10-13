# Go语言版本mdBook

这是 Go 语言实现的 mdBook 简化版工具。最初的想法是在 WASM 环境构建一个 mdBook 工具，用于 [《VS Code 插件开发》](https://github.com/chai2010/vscode-extdev-book) 案例。目前计划用于构建一些简单的电子书。

已经迁移到凹语言下，这个仓库不再更新: [https://pkg.go.dev/github.com/wa-lang/mnbook](https://pkg.go.dev/github.com/wa-lang/mnbook)

## 命令行

```
$ mdbook-go
NAME:
   mdbook-go - A tool for build markdown book

USAGE:
   mdbook-go [global options] command [command options] [arguments...]

COMMANDS:
   init   Creates a new book
   build  Builds a book from its markdown files
   serve  Serves a book at http://localhost:3000
   clean  Deletes a built book

GLOBAL OPTIONS:
   --help, -h  show help

 See "https://github.com/chai2010/mdbook-go" for more information.
```

- init: 初始化一个 Book 基础版本
- build: 将 Markdown 的 Book 构建为 html
- serve: 构建并启动服务, 方便本地查看效果
- clean: 删除构建的 book 子目录

## `book.toml` 文件

不支持注释，不支持未定义属性：

```toml
[book]
authors = ["chai2010"]
description = ""
language = "zh"
src = "."
title = "book title"

[output.html]
git-repository-icon = "fa-github"
git-repository-url = "https://github.com/chai2010/mdbook-go"
edit-url-template = "https://github.com/chai2010/mdbook-go/edit/master/testdata/{path}"
```

## `SUMMARY.md` 文件

```md
# Summary

[Preface](preface.md)

- [Chapter 1](./src/chapter_1.md)
  - [Chapter 1.1](./src/chapter_1.1.md)
  - [Chapter 1.2](./src/chapter_1.2.md)

- [Chapter 2](./src/chapter_2.md)

<!-- comment -->
```

## Markdown 文件

```md
# Chapter 1

[Github Repo](https://github.com/chai2010/mdbook-go): `[Github Repo](https://github.com/chai2010/mdbook-go)`


Image: `![](../images/video-001.png)`:

![](../images/video-001.png)

OK!
```

不支持内联 HTML。
