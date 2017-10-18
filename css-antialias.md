---
title: CSS antialiasing
category: CSS
layout: 2017/sheet
updated: 2017-08-26
intro: |
  Here's a 4-line snippet on how to get beautiful, antialiased text with CSS.
---

### 字体平滑
{: .-prime}

```css
* {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
```

### 支持

 * Firefox 25+ on OSX
 * Webkits (Chrome, Safari, etc)

## 参考
{: .-one-column}

 * [maxvoltar.com](http://maxvoltar.com/archive/-webkit-font-smoothing)
 * [maximilianhoffman.com](http://maximilianhoffmann.com/posts/better-font-rendering-on-osx)
 * [ilikekillnerds.com](http://ilikekillnerds.com/2010/12/a-solution-to-stop-font-face-fonts-looking-bold-on-mac-browsers/)
{: .-also-see}
