---
title: Awesome Redux
category: React
layout: 2017/sheet
updated: 2017-08-30
---

### redux-actions

以 flux 标准的 action 规范，创建一个 `action creators`。
{: .-setup}

```js
increment = createAction('INCREMENT', amount => amount)
increment = createAction('INCREMENT')  // same
```

```js
increment(42) === { type: 'INCREMENT', payload: 42 }
```

```js
// 处理错误：
err = new Error()
increment(err) === { type: 'INCREMENT', payload: err, error: true }
```

[redux-actions](https://www.npmjs.com/package/redux-actions)
{: .-crosslink}

### flux 标准的 action

flux action 对象的标准。一个 action 除了可能包含 `error`，`payload` 或者 `meta`，没有别的。
{: .-setup}

```js
{ type: 'ADD_TODO', payload: { text: 'Work it' } }
{ type: 'ADD_TODO', payload: new Error(), error: true }
```

[flux-standard-action](https://github.com/acdlite/flux-standard-action)
{: .-crosslink}

### redux-multi

在一个 `action creator` 中分发多个 `actions`。
{: .-setup}

```js
store.dispatch([
  { type: 'INCREMENT', payload: 2 },
  { type: 'INCREMENT', payload: 3 }
])
```

[redux-multi](https://github.com/ashaffer/redux-multi)
{: .-crosslink}

### reduce-reducers

合并 reducers，像 `combineReducers` 方法，不要使用命名空间。

{: .-setup}

```js
re = reduceReducers(
  (state, action) => state + action.number,
  (state, action) => state + action.number
)

re(10, { number: 2 })  //=> 14
```

[reduce-reducers](https://www.npmjs.com/package/reduce-reducers)
{: .-crosslink}

### redux-logger

输出 actions 到你的控制台。

{: .-setup}

```js
// 使用
import { applyMiddleware, createStore } from 'redux';
import { createLogger } from 'redux-logger'

const logger = createLogger({
  // ...options
});

const store = createStore(
  reducer,
  applyMiddleware(logger)
);
```

[redux-logger](https://github.com/evgenyrodionov/redux-logger)
{: .-crosslink}

异步
-----

### redux-promise

通过结合 promises 去分发一个 flux 标准的 action。

{: .-setup}

```js
increment = createAction('INCREMENT')  // redux-actions
increment(Promise.resolve(42))
```

[redux-promise](https://github.com/acdlite/redux-promise)
{: .-crosslink}

### redux-promises

Sorta like that, too. Works by letting you pass *thunks* (functions) to `dispatch()`. Also has 'idle checking'.
{: .-setup}

```js
fetchData = (url) => (dispatch) => {
  dispatch({ type: 'FETCH_REQUEST' })
  fetch(url)
    .then((data) => dispatch({ type: 'FETCH_DONE', data })
    .catch((error) => dispatch({ type: 'FETCH_ERROR', error })
})

store.dispatch(fetchData('/posts'))
```

```js
// That's actually shorthand for:
fetchData('/posts')(store.dispatch)
```

[redux-promises](https://www.npmjs.com/package/redux-promises)
{: .-crosslink}

### redux-effects

Pass side effects declaratively to keep your actions pure.
{: .-setup}

```js
{
  type: 'EFFECT_COMPOSE',
  payload: {
    type: 'FETCH'
    payload: {url: '/some/thing', method: 'GET'}
  },
  meta: {
    steps: [ [success, failure] ]
  }
}
```

[redux-effects](https://www.npmjs.com/package/redux-effects)
{: .-crosslink}

### redux-thunk

Pass "thunks" to as actions. Extremely similar to redux-promises, but has support for getState.
{: .-setup}

```js
fetchData = (url) => (dispatch, getState) => {
  dispatch({ type: 'FETCH_REQUEST' })
  fetch(url)
    .then((data) => dispatch({ type: 'FETCH_DONE', data })
    .catch((error) => dispatch({ type: 'FETCH_ERROR', error })
})

store.dispatch(fetchData('/posts'))
```

```js
// That's actually shorthand for:
fetchData('/posts')(store.dispatch, store.getState)
```

```js
// Optional: since fetchData returns a promise, it can be chained
// for server-side rendering
store.dispatch(fetchPosts()).then(() => {
  ReactDOMServer.renderToString(<MyApp store={store} />)
})
```

[redux-thunk](https://www.npmjs.com/package/redux-thunk)
{: .-crosslink}
