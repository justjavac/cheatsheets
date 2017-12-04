---
title: Redux
category: React
layout: 2017/sheet
updated: 2017-08-30
weight: -3
---

### 创建 store

```js
import { createStore } from 'redux'
```
{: .-setup}

```js
// Reducer
function counter (state = { value: 0 }, action) {
  switch (action.type) {
  case 'INCREMENT':
    return { value: state.value + 1 }
  case 'DECREMENT':
    return { value: state.value - 1 }
  default:
    return state
  }
}
```

```js
let store = createStore(counter)
```

```js
// 可选 - 您可以将 `initialState` 作为第二个参数传递
let store = createStore(counter, { value: 0 })
```

一个 store 由一个 reducer 函数创建，它保存当前的 `state`，并根据给出的 `action` 返回一个新的 `state`。

### 使用 store

```js
let store = createStore(counter)
```
{: .-setup}

```js
// 分发一个 action; 去改变 state
store.dispatch({ type: 'INCREMENT' })
store.dispatch({ type: 'DECREMENT' })
```

```js
// 得到当前的 state
store.getState()
```

```js
// 监听 state 的改变
store.subscribe(() => { ... })
```

分发 `actions` 去改变 `store` 的 `state`。

## React Redux

### Provider

```js
import { Provider } from 'react-redux'
```
{: .-setup}

```js
React.render(
  <Provider store={store}>
    <App />
  </Provider>, mountNode)
```

`<Provider>` 组件可以让你的 `React` 组件可获取 `store`。如需可以使用 `connect` 注入。

### 映射状态

```js
import { connect } from 'react-redux'
```
{: .-setup}

```js
// 函数式 React 组件
function App ({ messasge, onMessageClick }) {
  return (
    <div onClick={() => onMessageClick('hello')}>
      {message}
    </div>
  )
}
```

```js
// 映射 `state` 到 `props`：
// 这些将作为 props 添加到组件中。
function mapState (state) {
  return { message: state.message }
}

// 映射 `dispatch` 到 `props`:
// 同样组件可以通过 props 获取。
function mapDispatch (dispatch) {
  return {
    onMessageClick (message) {
      dispatch({ type: 'click', message })
    }
  }
}

// 注入到 App
export default connect(mapState, mapDispatch)(App)
```

### 简写

```js
export default connect(
  (state) => ({
    message: state.message
  })
  (dispatch) => ({
    onMessageClick: (message) => {
      dispatch({ type: 'click', message })
    }
  })
)(App)
```

较短的写法，效果相同。

## 中间件

### 签名

```js
// 无操作中间件
const logger = store => dispatch => action { dispatch(action) }
```

```js
const logger = store => {
  // 此函数在 createStore() 中运行
  // 返回一个 dispatch() 的装饰器

  return dispatch => {
    // 同样运行在 createStore() 中
    // 返回一个新的 dispatch() 函数

    return action => {
      // 运行每一个 dispatch()
    }
  }
}
```

中间件是 `dispatch()` 的简单装饰器，可以让你获取不同类型的 `actions`，并在接收 `actions` 时执行不同的任务。

### 应用中间件

```js
const enhancer = applyMiddleware(logger, thunk, ...)
```

```js
const store = createStore(reducer, {}, enhancer)
```
{: data-line="1"}

## 参考
{: .-one-column}

* [Redux](https://www.npmjs.com/package/redux) _(npmjs.com)_
* [React-redux](https://www.npmjs.com/package/react-redux) _(npmjs.com)_
* [Usage with React](http://redux.js.org/docs/basics/UsageWithReact.html) _(redux.js.org)_
{: .-also-see}
