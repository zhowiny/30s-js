---
title: 深度映射对象的`keys`。(Deep map object keys)
tags: object,recursion
expertise: advanced
cover: blog_images/duck-plants.jpg
firstSeen: 2018-11-29T15:22:53+02:00
lastUpdated: 2020-09-15T16:28:04+03:00
---

# 深度映射对象的 `keys` 。
> Deep maps an object's keys.

- 创建一个与提供的对象具有相同值的对象，并通过为每个键运行提供的函数生成键。
- 使用 `Object.keys()` 来迭代对象的键。
- 使用 `Array.prototype.reduce()` 创建一个具有相同值和映射键的新对象，使用 `fn`。

```js
const deepMapKeys = (obj, fn) =>
  Array.isArray(obj)
    ? obj.map(val => deepMapKeys(val, fn))
    : typeof obj === 'object'
    ? Object.keys(obj).reduce((acc, current) => {
        const key = fn(current);
        const val = obj[current];
        acc[key] =
          val !== null && typeof val === 'object' ? deepMapKeys(val, fn) : val;
        return acc;
      }, {})
    : obj;
```

```js
const obj = {
  foo: '1',
  nested: {
    child: {
      withArray: [
        {
          grandChild: ['hello']
        }
      ]
    }
  }
};
const upperKeysObj = deepMapKeys(obj, key => key.toUpperCase());
/*
{
  "FOO":"1",
  "NESTED":{
    "CHILD":{
      "WITHARRAY":[
        {
          "GRANDCHILD":[ 'hello' ]
        }
      ]
    }
  }
}
*/
```
