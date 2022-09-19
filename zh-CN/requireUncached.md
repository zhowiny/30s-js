---
title: 模块不缓存引入(Uncached module require)
tags: node
expertise: advanced
author: chalarangelo
cover: blog_images/curve.jpg
firstSeen: 2020-08-07T15:49:39+03:00
lastUpdated: 2020-09-15T16:28:04+03:00
---

### 从缓存中删除模块后加载模块（如果存在）。
> Loads a module after removing it from the cache (if exists).

- 使用 `delete` 从缓存中删除模块（如果存在）。
- 使用 `require()` 再次加载模块。

```js
const requireUncached = module => {
  delete require.cache[require.resolve(module)];
  return require(module);
};
```

```js
const fs = requireUncached('fs'); // 'fs' 每次都会重新加载
```
