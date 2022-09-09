---
title: 从路径字符串获取嵌套对象属性(Get nested object property from path string)
tags: object,regexp
expertise: intermediate
cover: blog_images/brown-bird.jpg
firstSeen: 2018-01-18T17:40:42+02:00
lastUpdated: 2020-10-19T22:49:51+03:00
---

### 从对象中检索由给定选择器指示的一组属性。
> Retrieves a set of properties indicated by the given selectors from an object.

- 对每个选择器使用 `Array.prototype.map()`，`String.prototype.replace()` 用点替换方括号。
- 使用 `String.prototype.split()` 来拆分每个选择器。
- 使用 `Array.prototype.filter()` 删除空值和 `Array.prototype.reduce()` 获取每个选择器指示的值。

```js
const get = (from, ...selectors) =>
  [...selectors].map(s =>
    s
      .replace(/\[([^\[\]]*)\]/g, '.$1.')
      .split('.')
      .filter(t => t !== '')
      .reduce((prev, cur) => prev && prev[cur], from)
  );
```

```js
const obj = {
  selector: { to: { val: 'val to select' } },
  target: [1, 2, { a: 'test' }],
};
get(obj, 'selector.to.val', 'target[0]', 'target[2].a');
// ['val to select', 1, 'test']
```
