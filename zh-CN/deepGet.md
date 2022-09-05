---
title: 基于 `keys` 数组获取嵌套对象中的值(Get nested value in object based on array of keys)
tags: object
expertise: intermediate
cover: blog_images/mask-quiet.jpg
firstSeen: 2019-05-09T13:30:52+03:00
lastUpdated: 2020-10-19T18:51:03+03:00
---

### 根据 `keys` 数组获取嵌套 JSON 对象中的目标值。
> Gets the target value in a nested JSON object, based on the `keys` array.

- 将嵌套 JSON 对象中所需的键作为“数组”进行比较。
- 使用 `Array.prototype.reduce()` 来一一获取嵌套 JSON 对象中的值。
- 如果对象中存在key，则返回目标值，否则返回`null`。

```js
const deepGet = (obj, keys) =>
  keys.reduce(
    (xs, x) => (xs && xs[x] !== null && xs[x] !== undefined ? xs[x] : null),
    obj
  );
```

```js
let index = 2;
const data = {
  foo: {
    foz: [1, 2, 3],
    bar: {
      baz: ['a', 'b', 'c']
    }
  }
};
deepGet(data, ['foo', 'foz', index]); // get 3
deepGet(data, ['foo', 'bar', 'baz', 8, 'foz']); // null
```
