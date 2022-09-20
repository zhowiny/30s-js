---
title: 字符串化循环引用的 JSON 对象 JSON(Stringify circular JSON)
tags: object
expertise: advanced
cover: blog_images/periscope.jpg
firstSeen: 2020-10-06T12:32:28+03:00
lastUpdated: 2020-10-22T20:24:30+03:00
---

### 将包含循环引用的 JSON 对象序列化为 JSON 格式。
> Serializes a JSON object containing circular references into a JSON format.

- 创建一个 `WeakSet` 来存储和检查看到的值，使用 `WeakSet.prototype.add()` 和 `WeakSet.prototype.has()`。
- 将 `JSON.stringify()` 与自定义替换函数一起使用，该函数会省略 `seen` 中已经存在的值，并根据需要添加新值。
- ⚠️ **注意：**此函数查找并删除循环引用，这会导致序列化 JSON 中的循环数据丢失。

```js
const stringifyCircularJSON = obj => {
  const seen = new WeakSet();
  return JSON.stringify(obj, (k, v) => {
    if (v !== null && typeof v === 'object') {
      if (seen.has(v)) return;
      seen.add(v);
    }
    return v;
  });
};
```

```js
const obj = { n: 42 };
obj.obj = obj;
stringifyCircularJSON(obj); // '{"n": 42}'
```
