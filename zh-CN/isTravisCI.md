---
title: 环境是 Travis CI(Environment is Travis CI)
tags: node
expertise: intermediate
unlisted: true
cover: blog_images/succulent-5.jpg
firstSeen: 2018-01-01T17:28:08+02:00
lastUpdated: 2020-10-20T23:02:01+03:00
---

# 检查当前环境是否为 [Travis CI](https://travis-ci.org/)。
> Checks if the current environment is [Travis CI](https://travis-ci.org/).

- 检查当前环境是否有 `TRAVIS` 和 `CI` 环境变量（[参考](https://docs.travis-ci.com/user/environment-variables/#Default-Environment-Variables)）。

```js
const isTravisCI = () => 'TRAVIS' in process.env && 'CI' in process.env;
```

```js
isTravisCI(); // true (如果代码跑在 Travis CI)
```
