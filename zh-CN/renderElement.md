---
title: 渲染 DOM 元素(Render DOM element)
tags: browser,recursion
expertise: advanced
author: chalarangelo
cover: blog_images/maple-leaf-palette.jpg
firstSeen: 2020-05-03T11:55:42+03:00
lastUpdated: 2021-10-13T19:29:39+02:00
---

# 将给定的 DOM 树渲染到指定的 DOM 元素中。
> Renders the given DOM tree in the specified DOM element.

- 将第一个参数分解为 `type` 和 `props`。 使用 `type` 来确定给定元素是否是文本元素。
- 根据元素的 `type`，使用 `Document.createTextNode()` 或 `Document.createElement()` 来创建 DOM 元素。
- 使用 `Object.keys()` 将属性添加到 DOM 元素并根据需要设置事件侦听器。
- 使用递归来渲染`props.children`，如果有的话。
- 最后，使用 `Node.appendChild()` 将 DOM 元素附加到指定的 `container`。

```js
const renderElement = ({ type, props = {} }, container) => {
  const isTextElement = !type;
  const element = isTextElement
    ? document.createTextNode('')
    : document.createElement(type);

  const isListener = p => p.startsWith('on');
  const isAttribute = p => !isListener(p) && p !== 'children';

  Object.keys(props).forEach(p => {
    if (isAttribute(p)) element[p] = props[p];
    if (!isTextElement && isListener(p))
      element.addEventListener(p.toLowerCase().slice(2), props[p]);
  });

  if (!isTextElement && props.children && props.children.length)
    props.children.forEach(childElement =>
      renderElement(childElement, element)
    );

  container.appendChild(element);
};
```

```js
const myElement = {
  type: 'button',
  props: {
    type: 'button',
    className: 'btn',
    onClick: () => alert('Clicked'),
    children: [{ props: { nodeValue: 'Click me' } }]
  }
};

renderElement(myElement, document.body);
```
