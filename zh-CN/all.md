---
title: 测试所有数组元素是否为真(Test if all array elements are truthy)
tags: array
expertise: beginner
cover: blog_images/touch-flower.jpg
firstSeen: 2018-02-14T11:46:15+02:00
lastUpdated: 2020-10-18T20:24:28+03:00
---
### 检查提供的谓词函数是否为集合中的所有元素返回 `true`。
> Checks if the provided predicate function returns `true` for all elements in a collection.

- 使用 `Array.prototype.every()` 来测试集合中的所有元素是否基于 `fn` 返回 `true`。
- 省略第二个参数，`fn`，使用 `Boolean` 作为默认值。

```js
const all = (arr, fn = Boolean) => arr.every(fn);
```

```js
all([4, 2, 3], x => x > 1); // true
all([1, 2, 3]); // true
```
