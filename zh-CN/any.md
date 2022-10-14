---
title: 测试任何数组元素是否为真(Test if any array element is truthy)
tags: array
expertise: beginner
cover: blog_images/basket-paper.jpg
firstSeen: 2018-02-14T11:46:15+02:00
lastUpdated: 2020-10-18T20:24:28+03:00
---

# 检查提供的谓词函数是否为集合中的至少一个元素返回`true`。
> Checks if the provided predicate function returns `true` for at least one element in a collection.

- 使用 `Array.prototype.some()` 来测试集合中是否有任何元素基于 `fn` 返回 `true`。
- 省略第二个参数，`fn`，使用 `Boolean` 作为默认值。

```js
const any = (arr, fn = Boolean) => arr.some(fn);
```

```js
any([0, 1, 2, 0], x => x >= 2); // true
any([0, 0, 1, 0]); // true
```
