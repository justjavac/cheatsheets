---
title: CSS
category: CSS
layout: 2017/sheet
tags: [WIP]
weight: -1
---

## Basics
{: .-three-column}

### 选择器

```css
.class {
  font-weight: bold;
}
```
{: .-setup}

| Selector | Description |
| --- | --- |
| `div` | Element |
| `.class` | Class |
| `#id` | ID |
| `[disabled]` | Attribute |
| `[role="dialog"]` | Attribute |

### 关系选择器

| Selector | Description |
| --- | --- |
| `.parent .child` | Descendant |
| `.parent > .child` | Direct descendant |
| `.child + .sibling` | Adjascent sibling |
| `.child ~ .sibling` | Far sibling |

### 属性选择器

| Selector | Description |
| --- | --- |
| `[role="dialog"]` | `=` Exact |
| `[class~="box"]` | `~=` Has word |
| `[class|="box"]` | `|=` Exact or prefix (eg, `value-`) |
| `[href$=".doc"]` | `$=` Ends in |
| `[class*="-is-"]` | `*=` Contains |

### 伪类选择器

| Selector | Description |
| --- | --- |
| `:target` | eg, `h2#foo:target` |
| --- | --- |
| `:disabled` | |
| `:focus` | |
| `:active` | |
| --- | --- |
| `:nth-child(3)` | 3rd child |
| `:nth-child(3n+2)` | 2nd child in groups of 3 |
| `:nth-child(-n+4)` | |
| --- | --- |
| `:nth-last-child(2)` | |
| `:nth-of-type(2)` | |
| --- | --- |

### 伪类扩展

| Selector |
| --- |
| `:first-of-type` |
| `:last-of-type` |
| `:nth-of-type(2)` |
| `:only-of-type` |
| --- |
| `:first-child` |
| `:last-child` |
| `:nth-child(2)` |
| `:only-child` |
{: .-left-align}

Fonts
-----
{: .-left-reference}

### 属性

| Property | Description |
| --- | --- |
| `font-family:` | `<font>, <fontN>` |
| `font-size:` | `<size>` |
| `letter-spacing:` | `<size>` |
| `line-height:` | `<number>` |
| --- | --- |
| `font-weight:` | `bold` `normal` |
| `font-style:` | `italic` `normal` |
| `text-decoration:` | `underline` `none` |
| --- | --- |
| `text-align:` | `left` `right` `center` `justify` |
| `text-transform:` | `capitalize` `uppercase` `lowercase` |
{: .-key-values}

### 速记
{: .-prime}

| `font:` | `italic` | `400`  | `14px`   | `/` | `1.5`       | `sans-serif` |
|         | style    | weight | size (required) |     | line-height | family (required)  |
{: .-css-breakdown}

### 示例

```css
font-family: Arial;
font-size: 12pt;
line-height: 1.5;
letter-spacing: 0.02em;
color: #aa3322;
```

### Case

```css
text-transform: capitalize; /* Hello */
text-transform: uppercase;  /* HELLO */
text-transform: lowercase;  /* hello */
```

Background
----------
{: .-left-reference}

### 属性

| Property                 | Description                              |
| ---                      | ---                                      |
| `background:`            | _(Shorthand)_                            |
| ---                      | ---                                      |
| `background-color:`      | `<color>`                                |
| `background-image:`      | `url(...)`                               |
| `background-position:`   | `left/center/right` `top/center/bottom`  |
| `background-size:`       | `cover` `X Y`                            |
| `background-clip:`       | `border-box` `padding-box` `content-box` |
| `background-repeat:`     | `no-repeat` `repeat-x` `repeat-y`        |
| `background-attachment:` | `scroll` `fixed` `local`                 |
{: .-key-values}

### 速记

| `background:` | `#ff0` | `url(bg.jpg)` | `left`    | `top`     | `/` | `100px` `auto` | `no-repeat` | `fixed;`   |
| `background:` | `#abc` | `url(bg.png)` | `center`  | `center`  | `/` | `cover`        | `repeat-x`  | `local; `  |
|               | color  | image         | positionX | positionY |     | size           | repeat      | attachment |
{: .-css-breakdown}

### 多背景

```css
background:
  linear-gradient(to bottom, rgba(0,0,0,0.5), rgba(0,0,0,0.5)),
  url('background.jpg') center center / cover,
  #333;
  ```

Animation
---------
{: .-left-reference}

### 属性

| `animation:` | _(shorthand)_ |
| `animation-name:` | `<name>` |
| `animation-delay:` | `<time>ms` |
| `animation-duration:` | `<time>ms` |
| `animation-direction:` | `normal` `reverse` `alternate` `alternate-reverse` |
| `animation-iteration-count:` | `infinite` `<number>` |
| `animation-timing-function:` | `ease` `linear` `ease-in` `ease-out` `ease-in-out` |
{: .-key-values}

### 速记

| `animation:` | `bounce` | `300ms` | `linear` | `100ms` | `infinite` | `alternate-reverse` |
| | name | duration | timing-function | delay | count | direction |
{: .-css-breakdown}

### 示例

```css
animation: bounce 300ms linear 0s infinite normal;
animation: bounce 300ms linear infinite;
animation: bounce 300ms linear infinite alternate-reverse;
```

### 事件

```js
.one('webkitAnimationEnd oanimationend msAnimationEnd animationend')
```
