---
title: 节点列表转数组(NodeList to array)
tags: browser,array
expertise: beginner
cover: blog_images/colors-mural.jpg
firstSeen: 2018-05-06T18:11:21+03:00
lastUpdated: 2020-10-21T21:54:53+03:00
---

# 将 `NodeList` 转换为数组。
> Converts a `NodeList` to an array.

- 在新数组中使用扩展运算符 (`...`) 将 `NodeList` 转换为数组。

```js
const nodeListToArray = nodeList => [...nodeList];
```

```js
nodeListToArray(document.childNodes); // [ <!DOCTYPE html>, html ]
```
