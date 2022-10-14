---
title: 处理用户输入类型更改(Handle user input change)
tags: browser,event
expertise: advanced
cover: blog_images/digital-nomad-12.jpg
firstSeen: 2017-12-29T17:41:53+02:00
lastUpdated: 2020-10-21T21:54:53+03:00
---

# 每当用户输入类型更改（`mouse` 或 `touch`）时运行回调。
> Runs the callback whenever the user input type changes (`mouse` or `touch`).

- 使用两个事件监听器。
- 假设最初是 `mouse` 输入并将 `'touchstart'` 事件监听器绑定到文档。
- 在 `touchstart` 上，使用 `performance.now()` 添加一个 `mousemove` 事件监听器来监听20ms内触发的两个连续的 `mousemove` 事件。
- 在任何一种情况下，使用输入类型作为参数运行回调。

```js
const onUserInputChange = callback => {
  let type = 'mouse',
    lastTime = 0;
  const mousemoveHandler = () => {
    const now = performance.now();
    if (now - lastTime < 20)
      (type = 'mouse'),
        callback(type),
        document.removeEventListener('mousemove', mousemoveHandler);
    lastTime = now;
  };
  document.addEventListener('touchstart', () => {
    if (type === 'touch') return;
    (type = 'touch'),
      callback(type),
      document.addEventListener('mousemove', mousemoveHandler);
  });
};
```

```js
onUserInputChange(type => {
  console.log('用户现在使用', type, '作为输入类型。');
});
```
