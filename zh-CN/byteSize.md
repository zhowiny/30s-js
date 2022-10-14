---
title: 字符串的字节长度(Byte size of string)
tags: string
expertise: beginner
cover: blog_images/mountain-lake-cottage-2.jpg
firstSeen: 2017-12-29T14:30:34+02:00
lastUpdated: 2020-10-18T23:04:45+03:00
---

# 返回字符串的长度（以字节为单位）。
> Returns the length of a string in bytes.

- 将给定的字符串转换为 [`Blob` 对象](https://developer.mozilla.org/en-US/docs/Web/API/Blob)。
- 使用 `Blob.size` 获取字符串的长度（以字节为单位）。

```js
const byteSize = str => new Blob([str]).size;
```

```js
byteSize('😀'); // 4
byteSize('Hello World'); // 11
```
