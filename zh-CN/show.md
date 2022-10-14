---
title: 显示元素(Show elements)
tags: browser,css
expertise: beginner
cover: blog_images/green-plant.jpg
firstSeen: 2017-12-28T23:33:21+02:00
lastUpdated: 2020-10-22T20:24:30+03:00
---

# 显示所有指定的元素。
> Shows all the elements specified.

- 使用扩展运算符 (`...`) 和 `Array.prototype.forEach()` 清除每个指定元素的 `display` 属性。

```js
const show = (...el) => [...el].forEach(e => (e.style.display = ''));
```

```js
show(...document.querySelectorAll('img'));
// 在页面上显示所有 <img> 元素
```
