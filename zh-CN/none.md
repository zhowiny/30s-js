---
title: 测试是否所有数组元素都是假的(Test if all array elements are falsy)
tags: array
expertise: beginner
cover: blog_images/bug.jpg
firstSeen: 2018-02-14T11:46:15+02:00
lastUpdated: 2020-10-21T21:54:53+03:00
---

### 检查提供的谓词函数是否为集合中的所有元素返回 `false`。
> Checks if the provided predicate function returns `false` for all elements in a collection.

- 使用 `Array.prototype.some()` 来测试集合中是否有任何元素基于 `fn` 返回 `true`。
- 省略第二个参数，`fn`，使用 `Boolean` 作为默认值。

```js
const none = (arr, fn = Boolean) => !arr.some(fn);
```

```js
none([0, 1, 3, 0], x => x == 2); // true
none([0, 0, 0]); // true
```
