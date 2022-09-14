---
title: 嵌套对象(数组转树)(Nest objects)
tags: object,recursion
expertise: intermediate
cover: blog_images/birds.jpg
firstSeen: 2018-02-24T13:49:56+02:00
lastUpdated: 2020-10-21T21:54:53+03:00
---

### 将相互关联的对象递归嵌套在一个平面数组中。
> Nests recursively objects linked to one another in a flat array.

- 使用递归。
- 使用 `Array.prototype.filter()` 过滤 `id` 与 `link` 匹配的项目。
- 使用 `Array.prototype.map()` 将每个项目映射到具有 `children` 属性的新对象，该属性根据哪些项目是当前项目的子项递归嵌套项目。
- 省略第二个参数 `id`，默认为 `null`，表示对象未链接到另一个对象（即它是顶级对象）。
- 省略第三个参数 `link`，使用 `parent_id` 作为默认属性，通过它的 `id` 将对象链接到另一个对象。

```js
const nest = (items, id = null, link = 'parent_id') =>
  items
    .filter(item => item[link] === id)
    .map(item => ({ ...item, children: nest(items, item.id, link) }));
```

```js
const comments = [
  { id: 1, parent_id: null },
  { id: 2, parent_id: 1 },
  { id: 3, parent_id: 1 },
  { id: 4, parent_id: 2 },
  { id: 5, parent_id: 4 }
];
const nestedComments = nest(comments);
// [{ id: 1, parent_id: null, children: [...] }]
```
