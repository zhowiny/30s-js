---
title: 将对象所有方法中的上下文绑定到对象(Bind all object methods)
tags: object,function
expertise: intermediate
cover: blog_images/laptop-with-code.jpg
firstSeen: 2018-01-26T14:14:53+02:00
lastUpdated: 2020-11-03T22:11:18+02:00
---

# 将对象的方法绑定到对象本身，覆盖现有方法。
> Binds methods of an object to the object itself, overwriting the existing method.

- 使用 `Array.prototype.forEach()` 迭代给定的 `fns`。
- 为每个返回一个函数，使用 `Function.prototype.apply()` 将给定的上下文（`obj`）应用于`fn`。

```js
const bindAll = (obj, ...fns) =>
  fns.forEach(
    fn => (
      (f = obj[fn]),
      (obj[fn] = function() {
        return f.apply(obj);
      })
    )
  );
```

```js
// before
var view = {
  label: 'docs',
  click: function() {
    console.log('clicked ' + this.label);
  }
};
document.body.addEventListener('click', view.click);
// Log 'clicked undefined' when clicked.
```

```js
// after
var view = {
  label: 'docs',
  click: function() {
    console.log('clicked ' + this.label);
  }
};
bindAll(view, 'click');
document.body.addEventListener('click', view.click);
// Log 'clicked docs' when clicked.
```
