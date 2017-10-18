---
title: Markdown
category: Markup
layout: 2017/sheet
prism_languages: [markdown]
updated: 2017-09-20
weight: -1
---

## 参考
{:.-three-column}

### 标题

```markdown
# h1
### h3
```

```markdown
标题 1
========
```

```markdown
标题 2
--------
```

### 强调

```markdown
*italic*
_italic_
```

```markdown
**bold**
__bold__
```

```markdown
`code`
```

### 链接

```markdown
[link](http://google.com)
```

```markdown
[link][google]
[google]: http://google.com
```

```markdown
<http://google.com>
```

### 图片

```markdown
![Image alt text](/path/to/img.jpg)
![Image alt text](/path/to/img.jpg "title")
![Image alt text][img]
```

```markdown
[img]: http://foo.com/img.jpg
```

### 代码

```
    4 个空格
    生成一个代码块
```

~~~markdown
```
code fences
```
~~~


~~~markdown
```js
codeFences.withLanguage()
```
~~~

### 引用

```markdown
> This is
> a blockquote
>
> > Nested
> > Blockquote
```

### 水平线

```markdown
----
```

```markdown
****
```
