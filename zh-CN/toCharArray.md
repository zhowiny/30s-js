---
title: 字符串转字符数组(String to character array)
tags: string
expertise: beginner
cover: blog_images/waving-over-lake.jpg
firstSeen: 2020-10-08T15:17:22+03:00
lastUpdated: 2020-10-08T15:17:22+03:00
---

# 将字符串转换为字符数组。
> Converts a string to an array of characters.

- 使用扩展运算符 (`...`) 将字符串转换为字符数组。

```js
const toCharArray = s => [...s];
```

```js
toCharArray('hello'); // ['h', 'e', 'l', 'l', 'o']
```
