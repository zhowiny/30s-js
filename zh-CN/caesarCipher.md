---
title: 凯撒密码(Caesar cipher)
tags: algorithm,string
expertise: beginner
author: maciv
cover: blog_images/ancient-greek-building.jpg
firstSeen: 2020-12-28T20:10:18+02:00
lastUpdated: 2020-12-29T12:29:21+02:00
---

### 使用凯撒密码加密或解密给定的字符串。
> Encrypts or decrypts a given string using the Caesar cipher.

- 使用模 (`%`) 运算符和三元运算符 (`?`) 计算正确的加密/解密密钥。
- 使用扩展运算符 (`...`) 和 `Array.prototype.map()` 迭代给定字符串的字母。
- 使用 `String.prototype.charCodeAt()` 和 `String.fromCharCode()` 适当地转换每个字母，忽略特殊字符、空格等。
- 使用 `Array.prototype.join()` 将所有字母组合成一个字符串。
- 将 `true` 传递给最后一个参数 `decrypt`，以解密加密的字符串。

```js
const caesarCipher = (str, shift, decrypt = false) => {
  const s = decrypt ? (26 - shift) % 26 : shift;
  const n = s > 0 ? s : 26 + (s % 26);
  return [...str]
    .map((l, i) => {
      const c = str.charCodeAt(i);
      if (c >= 65 && c <= 90)
        return String.fromCharCode(((c - 65 + n) % 26) + 65);
      if (c >= 97 && c <= 122)
        return String.fromCharCode(((c - 97 + n) % 26) + 97);
      return l;
    })
    .join('');
};
```

```js
caesarCipher('Hello World!', -3); // 'Ebiil Tloia!'
caesarCipher('Ebiil Tloia!', 23, true); // 'Hello World!'
```

> [凯撒密码(维基百科)](https://zh.wikipedia.org/zh-cn/%E5%87%B1%E6%92%92%E5%AF%86%E7%A2%BC)
>
> [凯撒加密法(百度百科)](https://baike.baidu.com/item/%E5%87%AF%E6%92%92%E5%8A%A0%E5%AF%86%E6%B3%95/9513286#1)
