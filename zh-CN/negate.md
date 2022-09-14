---
title: 否定谓词函数(Negate predicate)
tags: function
expertise: beginner
cover: blog_images/blue-bird.jpg
firstSeen: 2017-12-24T08:28:52+02:00
lastUpdated: 2020-09-15T16:28:04+03:00
---

### 否定一个谓词函数
> Negates a predicate function.

- 获取一个谓词函数并将非运算符（`!`）及其参数应用于它。

```js
const negate = func => (...args) => !func(...args);
```

```js
[1, 2, 3, 4, 5, 6].filter(negate(n => n % 2 === 0)); // [ 1, 3, 5 ]
```
