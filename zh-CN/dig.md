---
title: 获取对象中的嵌套值(Get nested value in object)
tags: object,recursion
expertise: intermediate
cover: blog_images/brown-bird.jpg
firstSeen: 2018-07-08T23:06:24+03:00
lastUpdated: 2020-10-19T18:51:03+03:00
---

# 根据给定键获取嵌套 JSON 对象中的目标值。
> Gets the target value in a nested JSON object, based on the given key.

- 使用 `in` 运算符检查 `obj` 中是否存在 `target`。
- 如果找到，返回 `obj[target]` 的值。
- 否则使用 `Object.values()` 和 `Array.prototype.reduce()` 在每个嵌套对象上递归调用 `dig` 直到找到第一个匹配的键/值对。

```js
const dig = (obj, target) =>
  target in obj
    ? obj[target]
    : Object.values(obj).reduce((acc, val) => {
        if (acc !== undefined) return acc;
        if (typeof val === 'object') return dig(val, target);
      }, undefined);
```

```js
const data = {
  level1: {
    level2: {
      level3: 'some data'
    }
  }
};
dig(data, 'level3'); // 'some data'
dig(data, 'level4'); // undefined
```
