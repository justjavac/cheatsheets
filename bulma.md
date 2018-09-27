---
title: Bulma
layout: 2017/sheet
prism_languages: [css, html]
weight: -1
updated: 2018-03-06
authors:
  - github: benolot
description: |
  Basic guide on how to use Bulma, the lightweight css flexbox framework.
---

### 屏幕尺寸

```
         768         1024                1216         1408
'     '     '     '     '     '     '     '     '     '     '     '
<---------^------------^------------------^-------------^------------->
  mobile      tablet         desktop         widescreen      fullhd
```

### 列

```css
.container
```
'.columns' 作为容器,根据你的喜好在其中添加更多的 '.column' 元素
```html
<div class="columns">
    <div class="column"></div>
    <div class="column"></div>
    <div class="column"></div>
    <div class="column"></div>
    <div class="column"></div>
</div>
```

### 修饰符

以下CSS类会影响 **颜色**.

```css
.is-primary
.is-link
.is-info
.is-success
.is-warning
.is-danger
```

以下类改变 **大小**.
```css
.is-small
.is-medium
.is-large
```

以下类改变 **状态**.
```scss
.is-outlined
.is-loading
```


### 排版辅助类

以下类改变 **font-size**

| Class         | Font-size             |
| ---           | ---                   |
| `.is-size-1`  | 3rem                  |
| `.is-size-2`  | 2.5rem                |
| `.is-size-3`  | 2rem                  |
| `.is-size-4`  | 1.5rem                |
| `.is-size-5`  | 1.25rem               |
| `.is-size-6`  | 1rem                  |
| `.is-size-7`  | 0.75rem               |

以下类**对齐**文本

| Class                 | Alignment                              |
| ---                   | ---                                    |
| `.has-text-centered`  | 使文本 **居中**                         |
| `.has-text-justified` | 使文本 **两端对齐**                     |
| `.has-text-left`.     | 使文本 **左对齐**                       |
| `.has-text-right`     | 使文本 **右对齐**                       |

以下类**转换**文本

| Class              | Transformation                                     |
| ---                | ---                                                |
| `.is-capitalized`  | 将每个单词的 **第一个字符** 转换为 **大写**          |
| `.is-lowercase`    | 将 **所有** 字符转换为 **小写**                     |
| `.is-uppercase`    | 将 **所有** 字符转换为 **大写**                     |
