---
title: 检测设备类型(Detect device type)
tags: browser,regexp
expertise: intermediate
cover: blog_images/clutter-2.jpg
firstSeen: 2017-12-24T09:39:23+02:00
lastUpdated: 2020-10-22T20:23:47+03:00
---

# 检测页面是在移动设备还是桌面上查看。
> Detects whether the page is being viewed on a mobile device or a desktop.

- 使用正则表达式测试 `Navigator.userAgent` 属性以确定设备是移动设备还是桌面设备。

```js
const detectDeviceType = () =>
  /Android|webOS|iPhone|iPad|iPod|BlackBerry|IEMobile|Opera Mini/i.test(
    navigator.userAgent
  )
    ? 'Mobile'
    : 'Desktop';
```

```js
detectDeviceType(); // 'Mobile' or 'Desktop'
```
