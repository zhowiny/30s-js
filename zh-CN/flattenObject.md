---
title: 扁平化对象(Flatten object)
tags: object,recursion
expertise: advanced
cover: blog_images/lighthouse.jpg
firstSeen: 2018-02-07T11:30:18+02:00
lastUpdated: 2020-10-19T18:51:03+03:00
---

### 使用 `key` 的路径展平对象。
> Flattens an object with the paths for keys.

- 使用递归。
- 使用 `Object.keys()` 结合 `Array.prototype.reduce()` 将每个叶节点转换为扁平路径节点。
- 如果键的值是一个对象，该函数使用适当的 `prefix` 调用自身以使用 `Object.assign()` 创建路径。
- 否则，它将适当的前缀键值对添加到累加器对象。
- 你应该总是省略第二个参数，`prefix`，除非你希望每个键都有一个前缀。

```js
const flattenObject = (obj, prefix = '') =>
  Object.keys(obj).reduce((acc, k) => {
    const pre = prefix.length ? `${prefix}.` : '';
    if (
      typeof obj[k] === 'object' &&
      obj[k] !== null &&
      Object.keys(obj[k]).length > 0
    )
      Object.assign(acc, flattenObject(obj[k], pre + k));
    else acc[pre + k] = obj[k];
    return acc;
  }, {});
```

```js
flattenObject({ a: { b: { c: 1 } }, d: 1 }); // { 'a.b.c': 1, d: 1 }
```
