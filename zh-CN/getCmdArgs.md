---
title: 命令行参数(Command-line arguments)
tags: node
expertise: beginner
author: chalarangelo
cover: blog_images/terminal.jpg
firstSeen: 2022-04-26T05:00:00-04:00
---

# 获取传递给 Node.js 脚本的命令行参数。
> Gets the command-line arguments passed to a Node.js script.

- 使用 `process.argv` 获取所有命令行参数的数组。
- 使用 `Array.prototype.slice()` 删除前两个元素（Node.js 可执行文件的路径和正在执行的文件）。

```js
const getCmdArgs = () => process.argv.slice(2);
```

```js
// node my-script.js --name=John --age=30
getCmdArgs(); // ['--name=John', '--age=30']
```
