---
title: 恢复展开对象(Unflatten object)
tags: object
expertise: advanced
cover: blog_images/purple-flower-bunch.jpg
firstSeen: 2018-02-07T11:30:18+02:00
lastUpdated: 2020-10-22T20:24:44+03:00
---

### 使用键的路径恢复展开对象。
> Unflatten an object with the paths for keys.

- 使用嵌套的 `Array.prototype.reduce()` 将平面路径转换为叶节点。
- 使用 `String.prototype.split()` 用点分隔符拆分每个键，并使用 `Array.prototype.reduce()` 来针对键添加对象。
- 如果当前累加器已经包含针对特定键的值，则返回其值作为下一个累加器。
- 否则，将适当的键值对添加到累加器对象中，并将值作为累加器返回。

```js
const unflattenObject = obj =>
  Object.keys(obj).reduce((res, k) => {
    k.split('.').reduce(
      (acc, e, i, keys) =>
        acc[e] ||
        (acc[e] = isNaN(Number(keys[i + 1]))
          ? keys.length - 1 === i
            ? obj[k]
            : {}
          : []),
      res
    );
    return res;
  }, {});
```

```js
unflattenObject({ 'a.b.c': 1, d: 1 }); // { a: { b: { c: 1 } }, d: 1 }
unflattenObject({ 'a.b': 1, 'a.c': 2, d: 3 }); // { a: { b: 1, c: 2 }, d: 3 }
unflattenObject({ 'a.b.0': 8, d: 3 }); // { a: { b: [ 8 ] }, d: 3 }
```
