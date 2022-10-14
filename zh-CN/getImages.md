---
title: 从元素中获取所有图片(Get all images in element)
tags: browser
expertise: intermediate
cover: blog_images/portal-timelapse.jpg
firstSeen: 2018-10-07T16:24:36+03:00
lastUpdated: 2020-10-22T20:23:47+03:00
---

# 从一个元素中获取所有图像并将它们放入一个数组中。
> Fetches all images from within an element and puts them into an array.

- 使用 `Element.getElementsByTagName()` 获取提供的元素内的所有 `<img>` 元素。
- 使用 `Array.prototype.map()` 映射每个 `<img>` 元素的每个 `src` 属性。
- 如果 `includeDuplicates` 为 `false`，则创建一个新的 `Set` 以消除重复项，并在扩散到数组后返回。
- 省略第二个参数，`includeDuplicates`，默认丢弃重复项。

```js
const getImages = (el, includeDuplicates = false) => {
  const images = [...el.getElementsByTagName('img')].map(img =>
    img.getAttribute('src')
  );
  return includeDuplicates ? images : [...new Set(images)];
};
```

```js
getImages(document, true); // ['image1.jpg', 'image2.png', 'image1.png', '...']
getImages(document, false); // ['image1.jpg', 'image2.png', '...']
```
