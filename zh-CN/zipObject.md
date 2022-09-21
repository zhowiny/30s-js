---
title: 将数组分组为对象(Group array into object)
tags: array,object
expertise: intermediate
cover: blog_images/baloons-field.jpg
firstSeen: 2017-12-21T00:55:18+02:00
lastUpdated: 2020-10-22T20:24:44+03:00
---

### 将属性与值关联，给定有效的属性标识符数组和值数组。
> Associates properties to values, given array of valid property identifiers and an array of values.

- 使用 `Array.prototype.reduce()` 从两个数组构建一个对象。
- 如果 `props` 的长度比 `values` 长，剩余的键将是 `undefined`。
- 如果 `values` 的长度比 `props` 长，剩余的值将被忽略。

```js
const zipObject = (props, values) =>
  props.reduce((obj, prop, index) => ((obj[prop] = values[index]), obj), {});
```

```js
zipObject(['a', 'b', 'c'], [1, 2]); // {a: 1, b: 2, c: undefined}
zipObject(['a', 'b'], [1, 2, 3]); // {a: 1, b: 2}
```
