---
title: 环境是 Node.js(Environment is Node.js)
tags: node,browser
expertise: intermediate
cover: blog_images/cloudy-rock-formation.jpg
firstSeen: 2020-10-12T20:01:21+03:00
lastUpdated: 2021-04-02T11:45:13+03:00
---

### 确定当前运行时环境是否为 Node.js。
> Determines if the current runtime environment is Node.js.

- 使用提供有关当前 Node.js 进程信息的 `process` 全局对象。
- 检查是否定义了 `process`、`process.versions` 和 `process.versions.node`。

```js
const isNode = () =>
  typeof process !== 'undefined' &&
  !!process.versions &&
  !!process.versions.node;
```

```js
isNode(); // true (Node)
isNode(); // false (browser)
```
