---
title: ES2015+
category: JavaScript
layout: 2017/sheet
tags: [Featured]
updated: 2017-10-02
weight: -10
intro: |
  A quick overview of new JavaScript features in ES2015, ES2016, ES2017 and beyond.
---

### 块级作用域

#### Let

```js
function fn () {
  let x = 0
  if (true) {
    let x = 1 // only inside this `if`
  }
}
```
{: data-line="2,4"}

#### Const

```js
const a = 1
```

`let` 类似于 `var`. `Const` 的性质类似于 `let`, 但是声明后值不能改变.
See: [Let and const](http://babeljs.io/docs/learn-es2015/#let-const)

### 反引号字符串

#### 字符串插值

```js
var message = `Hello ${name}`
```

#### 多行字符串

```js
var str = `
hello
world
`
```

模板字符串和多行字符串。
查看: [模板字符串](http://babeljs.io/docs/learn-es2015/#template-strings)

### 二进制和八进制文字

```js
let bin = 0b1010010
let oct = 0o755
```

查看: [二进制和八进制文字](http://babeljs.io/docs/learn-es2015/#binary-and-octal-literals)

### 新方法

#### 新的字符串方法

```js
"hello".repeat(3)
"hello".contains("ll")
"\u1E9B\u0323".normalize("NFC")
```

查看: [New methods](http://babeljs.io/docs/learn-es2015/#math-number-string-object-apis)

### Classes类

```js
class Circle extends Shape {
```

#### Constructor

```js
  constructor (radius) {
    this.radius = radius
  }
```
{: data-line="1"}

#### Methods

```js
  getArea () {
    return Math.PI * 2 * this.radius
  }
```
{: data-line="1"}

#### 调用父级方法

```js
  expand (n) {
    return super.expand(n) * Math.PI
  }
```
{: data-line="2"}

#### 静态方法

```js
  static createFromDiameter(diameter) {
    return new Circle(diameter / 2)
  }
}
```
{: data-line="1"}

原型的语法糖.
查看: [Classes](http://babeljs.io/docs/learn-es2015/#classes)

### Exponent operator

```js
const byte = 2 ** 8
// Same as: Math.pow(2, 8)
```
{: data-line="1"}

Promises
--------
{: .-three-column}

### 创建 promises

```js
new Promise((resolve, reject) => {
  if (ok) { resolve(result) }
  else { reject(error) }
})
```
{: data-line="1"}

用于异步编程.
查看: [Promises](http://babeljs.io/docs/learn-es2015/#promises)

### 使用 promises

```js
promise
  .then((result) => { ··· })
  .catch((error) => { ··· })
```
{: data-line="2,3"}

### Promise 方法

```js
Promise.all(···)
Promise.race(···)
Promise.reject(···)
Promise.resolve(···)
```

Destructuring
-------------
{: .-three-column}

### 解构参数

#### Arrays

```js
var [first, last] = ['Nikola', 'Tesla']
```

#### Objects

```js
let {title, author} = {
  title: 'The Silkworm',
  author: 'R. Galbraith'
}
```
{: data-line="1"}

支持数组和对象.
查看: [Destructuring](http://babeljs.io/docs/learn-es2015/#destructuring)


### 函数参数

```js
function greet({ name, greeting }) {
  console.log(`${greeting}, ${name}!`)
}
```
{: data-line="1"}

```js
greet({ name: 'Larry', greeting: 'Ahoy' })
```

### 循环

```js
for (let {title, artist} in songs) {
  ···
}
```
{: data-line="1"}

赋值表达式也能运行在循环中.

Functions
---------

### 函数参数

#### Default arguments

```js
function greet (name = "Jerry") {
  return `Hello ${name}`
}
```
{: data-line="1"}

#### Rest arguments

```js
function fn(x, ...y) {
  // y is an Array
  return x * y.length
}
```
{: data-line="1"}

#### Spread

```js
fn(...[1, 2, 3])
// same as fn(1, 2, 3)
```
{: data-line="1"}

Default, rest, spread.
See: [Function arguments](http://babeljs.io/docs/learn-es2015/#default-rest-spread)

### 箭头函数

#### Fat arrows

```js
setTimeout(() => {
  ···
})
```
{: data-line="1"}

#### 传参

```js
readFile('text.txt', (err, data) => {
  ...
})
```
{: data-line="1"}

#### 隐形返回
```js
numbers.map(n => n * 2)
// No curly braces = implicit return
// Same as: numbers.map(function (n) { return n * 2 })
```
{: data-line="1"}

与 functions 类似但是 `this` 被隐式创建并且不可变.
查看: [Fat arrows](http://babeljs.io/docs/learn-es2015/#arrows)

Objects
-------

### 语法速记

```js
module.exports = { hello, bye }
// Same as: module.exports = { hello: hello, bye: bye }
```

查看: [对象字面量增强](http://babeljs.io/docs/learn-es2015/#enhanced-object-literals)

### 方法

```js
const App = {
  start () {
    console.log('running')
  }
}
// Same as: App = { start: function () {···} }
```
{: data-line="2"}

查看: [对象字面量增强](http://babeljs.io/docs/learn-es2015/#enhanced-object-literals)

### Getters 和 setters

```js
const App = {
  get closed () {
    return this.status === 'closed'
  },
  set closed (value) {
    this.status === value ? 'closed' : 'open'
  }
}
```
{: data-line="2,5"}

查看: [对象字面量增强](http://babeljs.io/docs/learn-es2015/#enhanced-object-literals)

### 计算属性名称

```js
let event = 'click'
let handlers = {
  ['on' + event]: true
}
// Same as: handlers = { 'onclick': true }
```
{: data-line="3"}

查看: [对象字面量增强](http://babeljs.io/docs/learn-es2015/#enhanced-object-literals)

Modules
-------

### Imports

```js
import 'helpers'
// aka: require('···')
```

```js
import Express from 'express'
// aka: Express = require('···').default || require('···')
```

```js
import { indent } from 'helpers'
// aka: indent = require('···').indent
```

```js
import * as Helpers from 'helpers'
// aka: Helpers = require('···')
```

```js
import { indentSpaces as indent } from 'helpers'
// aka: indent = require('···').indentSpaces
```

`import` 类似于 `require()`.
查看: [Module imports](http://babeljs.io/docs/learn-es2015/#modules)

### Exports

```js
export default function () { ··· }
// aka: module.exports.default = ···
```

```js
export function mymethod () { ··· }
// aka: module.exports.mymethod = ···
```

```js
export const pi = 3.14159
// aka: module.exports.pi = ···
```

`export` 类似于 `module.exports`.
查看: [Module exports](http://babeljs.io/docs/learn-es2015/#modules)

Generators
----------

### Generators

```js
function* idMaker () {
  var id = 0
  while (true) { yield id++ }
}
```

```js
var gen = idMaker()
gen.next().value  // → 0
gen.next().value  // → 1
gen.next().value  // → 2
```

查看: [Generators](http://babeljs.io/docs/learn-es2015/#generators)

### For..of 循环

```js
for (let i of iterable) {
  ···
}
```

用于遍历 generators 函数和数组.
查看: [For..of iteration](http://babeljs.io/docs/learn-es2015/#iterators-for-of)
