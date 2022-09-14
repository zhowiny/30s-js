---
title: 记忆函数(Memoize function)
tags: function
expertise: advanced
cover: blog_images/hard-disk.jpg
firstSeen: 2017-12-31T13:55:55+02:00
lastUpdated: 2020-10-21T21:54:53+03:00
---

### 返回记忆（缓存）的函数。
> Returns the memoized (cached) function.

- 通过实例化一个新的 `Map` 对象来创建一个空缓存。
- 返回一个函数，该函数接受单个参数提供给记忆函数，方法是首先检查该特定输入值的函数输出是否已经缓存，如果没有，则存储并返回它。
- 必须使用 `function` 关键字，以允许记忆函数在必要时更改其 `this` 上下文。
- 通过将其设置为返回函数的属性来允许访问 `cache`。

```js
const memoize = fn => {
  const cache = new Map();
  const cached = function (val) {
    return cache.has(val)
      ? cache.get(val)
      : cache.set(val, fn.call(this, val)) && cache.get(val);
  };
  cached.cache = cache;
  return cached;
};
```

```js
// 请参阅 `anagrams` 片段。
const anagramsCached = memoize(anagrams);
anagramsCached('javascript'); // 需要很长的时间
anagramsCached('javascript'); // 几乎立即返回，因为它被缓存了
console.log(anagramsCached.cache); // 缓存的anagrams map
```
