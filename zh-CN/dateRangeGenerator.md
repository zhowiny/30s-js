---
title: 日期范围生成器(Date range generator)
tags: date,function,generator
expertise: advanced
author: maciv
cover: blog_images/portal-timelapse.jpg
firstSeen: 2021-06-21T05:00:00-04:00
---

# 创建一个生成器，它使用给定的步骤生成给定范围内的所有日期。
> Creates a generator, that generates all dates in the given range using the given step.

- 使用`while`循环从`start`迭代到`end`，使用`yield`返回范围内的每个日期，使用`Date`构造函数。
- 使用 `Date.prototype.getDate()` 和 `Date.prototype.setDate()` 在返回每个后续值后增加 `step` 天。
- 省略第三个参数 `step`，使用默认值 `1`。

```js
const dateRangeGenerator = function* (start, end, step = 1) {
  let d = start;
  while (d < end) {
    yield new Date(d);
    d.setDate(d.getDate() + step);
  }
};
```

```js
[...dateRangeGenerator(new Date('2021-06-01'), new Date('2021-06-04'))];
// [ 2021-06-01, 2021-06-02, 2021-06-03 ]
```
