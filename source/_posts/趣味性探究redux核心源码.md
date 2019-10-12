---
title: 趣味性探究redux核心源码
date: 2019-03-16 15:51:05
tags: 
- redux
- react
- 中间件
- 数据存储
- 源码解析
categories: 前端
keywords:
- redux
- 数据存储
- 源码解析
- react
- 中间件
---

团队的项目中用了很久的 __react__ 和 __redux__，一值想弄懂 __redux__ 数据存储背后的逻辑，前段时间研究了下官方源码分享出来。这篇文章试图通过形象化的场景模拟来解读 __redux__ 背后的设计，这种方式可能印象会更加深刻些。

{% asset_img 1.png %}

<!-- more -->

## redux的核心功能
+ state: 存储着所有的数据变量
+ store: 可以简单描述成一个控制中心，可以获取 state，也可以改变 state，但是改变 state 需通过间接的方式
+ reducer: 将 state 和其中变量的最新数据做一次合并
+ action: 管理着改变 state 某些数据的行为，操作是同步的
+ asyncAction: 管理着改变 state 某些数据的行为，操作是异步的，比如请求接口

项目也常用到中间件比如 __thunk__
+ thunk: 可以嵌套触发 action

## 场景转换

如果看不大懂上面的概念，没关系，或许看过下面的场景后会有一些认识的转变

我试图将上面的 功能做一下场景的转变，场景是到店里吃饭，是生活中经常发生在你我身上的事情。如下我对功能做了标记，其中容器并非redux的功能，而是类似为一个页面

+ 容器: 餐桌
+ state: 餐桌上的所有菜品
+ store: 顾客
+ reducer: 顾客更新桌上的菜品区和碗碟区
+ action: 拿纸巾、加餐具、舔茶水、摆菜品
+ asyncAction: 取菜品
+ thunk: 服务员

> 顾客是整个就餐过程的核心人物，他可以吩咐服务员做各种事情，包括拿纸巾、上餐具、加茶水等简单的事情，这样，我们定义两种事情，一种是不需要等很久（大概一分钟）就能完成的事情比如上面提到的拿纸巾、上餐具、加茶水等叫简单事情。另一种是包含了需要等很久才能完成的事情比如到取菜品（需要后厨制作很久）等，叫复杂事情。

> 好了，两位顾客到了餐桌后开始点菜了，他们点了A、B、C三道菜品，服务员吩咐厨房开始制作并准备10分钟后去取菜品，餐桌上目前只有一份纸巾和一套餐具。

> 坐下来一小会儿，顾客发现少了一份餐具，于是叫服务员拿份餐具，服务员取来餐具交给了顾客，顾客放在餐桌自己的碗碟区。
> 又过了一会儿，顾客有点渴了，叫来服务员端两杯茶水，服务员取了两杯茶水交给顾客，顾客放在了餐桌自己的碗碟区。

> 10分钟过去了，服务员将三道菜品端上来了，放在旁边的菜品柜上，顾客将三道菜品摆放到了餐桌的菜品区。

> 没过过久，菜吃得差不多了，顾客吩咐服务员加一道菜D，顺便添加些茶水，于是服务员吩咐厨房做菜2分钟后来取，并且给顾客杯子加一些茶水，顾客将茶水放在了餐桌碗碟区。

> 2分钟过后，服务员将菜品D端上来了给到顾客，顾客摆放到了餐桌菜品区。

> 就餐的过程中两位顾客相聊甚换，吃得差不多了准备起身结账时，发现餐桌上有一份纸巾，顾客并不需要这个纸巾，于是叫服务员拿掉了这个纸巾。

> 最后顾客完成了结账。


看到这儿，如果能看到，其实 __redux__ 底部的设计已经明白差不多了，是不是很简单，其实也并没有那么难。
好了，为了将这个故事反应到 __redux__ 的设计上，我准备将关键信息和 __redux__ 的关键功能对应上。

如此，我们已经知道 __redux__ 面对一个 __action__ 的内部处理流程了，之所以需要这么规范化复杂化的流程设计，想必就是各司其职，防止越位，最后防止 __state__ 被恶意篡改。

## 开启源码解读

这篇文章就这么结束了吗，想的美，接下来就是重头戏。

对 redux 的设计有了一些认识后，我们结合它的核心源码来探究它是怎么完成上面的设计的，源码使用的是 [gh-pages](https://github.com/reduxjs/redux/tree/gh-pages/src) 版本，只提取其中的核心部分，下面是 redux 的 github 源码目录，包括 __creatStore__、__compose__、__combineReducers__、__applyMiddleware__，我们暂且略过 __bindActionCreators__，并引入 __thunk__ 一起看看他们是怎么结合的。

<div style="width:60%;margin:auto">{% asset_img 3.png %}</div>

### 场景转为示例

首先抛出一个具体的示例，仿真一开始的故事情节编写。为了模拟多个 reducer，我们将加餐具、舔茶水、摆菜品的操作看成一个模块，针对纸巾的操作看成另一个模块。

这是 reducer1，存储着餐具、茶水、菜品的初始化数据，以及更改这些数据的操作

``` js

// reducer1.js

import { ADD_TABLEWARE, ADD_TEA } from '@store/actions/action1';

const initialState = {
  tablewareCount: 1,
  teaCount: 0,
  dishs: [],
}

export default (state = initialState, action = {}) {
    case ADD_TABLEWARE:
      return state.merge({
        tablewareCount: action.tablewareCount,
      });
    case ADD_TEA:
      return state.merge({
        teaCount: action.teaCount,
      });
    case PLACE_DISHS:
      return state.merge({
        dishs: action.dishs,
      });
    default:
      return state;
}

```

这是 action1，对应着 reducer1，标识着改变 state 某些数据的操作行为，包括加餐具、舔茶水、摆菜品，当然也可以对数据做一些处理后转为最终态


``` js

// action1.js

export const ADD_TABLEWARE = 'ADD_TABLEWARE';
export const ADD_TEA = 'ADD_TEA';
export const PLACE_DISHS = 'PLACE_DISHS';

export function addTablewareAction(count) {
  return {
    type: ADD_TABLEWARE,
    tablewareCount: count,
  };
}

export function addTeaAction(count) {
  return {
    type: ADD_TEA,
    teaCount: count,
  };
}

export function placeDishsAction(dishs) {
  return {
    type: PLACE_DISHS,
    dishs,
  };
}

```

这是 asyncAction1，在这里的 action 都包含有异步操作，通常是请求接口数据，包括取菜品


``` js

// asyncAction1.js

import dish from '@api/dish';
import { placeDishsAction, addTeaAction } from '@store/actions/action1';

export const getDishs = () => (dispatch, getState) => {
  dish.getDishAPI()
    .then((res) => {
      const { dishs } = res.data;
      const teaCount = 2;
      dispatch(placeDishsAction(dishs));
      dispatch(addTeaAction(teaCount));
    })
}

```

这是reducer2，存储针对纸巾的操作和纸巾初始数据

``` js

// reducer2.js

import { MINUS_NAPKIN } from '@store/actions/action2';

const initialState = {
  napkinCount: 1,
}

export default (state = initialState, action = {}) {
    case MINUS_NAPKIN:
      return state.merge({
        napkinCount: action.napkinCount,
      });
    default:
      return state;
}

```

这是 action2，对应着 reducer2，包含对纸巾的删除操作

``` bash

#action2.js

export const MINUS_NAPKIN = 'MINUS_NAPKIN';

export deleteNapkin = {
  type: MINUS_NAPKIN,
  napkinCount: count,
}

```

这里是生成控制中心 store 的地方，也就是顾客

``` js

// store.js

import { createStore, compose, applyMiddleware, combineReducers} from 'redux';
import thunk from 'redux-thunk';
import reducer1 from './reducers/reducer1';
import reducer2 from './reducers/reducer2';

const rootReducer = combineReducers({
  reducer1,
  reducer2
});

const composeEnhancers = window.__REDUX_DEVTOOLS_EXTENSION_COMPOSE__ || compose;
const store = createStore(rootReducer, composeEnhancers(
  applyMiddleware(thunk),
));

export default store;

```

至此，我们完成了一个 redux 的基本结构，包括两个 reducer 及对应的 action，同时还有一个 asyncAction 以模拟包含异步的操作（取菜品对应请求接口这种类似的操作），最后在 store.js 中做两个 reducer 的合并，同时引入中间件 thunk 做 store 初始化。之后就是页面引入这个 store 就可以做相关的业务逻辑了，这块的会涉及到 react-redux 相关，到时会单独来讲解，在这里咱们只关注 redux 的内部实现。

### createStore

接下来就是，怎么去看redux这个源码，我们顺着store的初始化来看，因为这是页面逻辑唯一引入redux的地方。可以看到有几个函数我们需要关注
+ combineReducers
+ createStore
+ composeEnhancers
+ applyMiddleware
+ thunk

其实这基本是今天要说的全部内容了。

首先看 createStore，这是 store 初始化的地方，我们剔除源码中的异常等逻辑，只提取核心逻辑来看。

``` js

// 来源 redux 中的 createStore.js，做了部分修改，剔除了replaceReducer和[$$observable]

export default function createStore(reducer, preloadedState, enhancer) {
  if (typeof preloadedState === 'function' && typeof enhancer === 'undefined') {
    enhancer = preloadedState
    preloadedState = undefined
  }

  if (typeof enhancer !== 'undefined') {
    if (typeof enhancer !== 'function') {
      throw new Error('Expected the enhancer to be a function.')
    }

    return enhancer(createStore)(reducer, preloadedState)
  }

  let currentReducer = reducer
  let currentState = preloadedState
  let currentListeners = []
  let nextListeners = currentListeners
  function getState() {
    return currentState
  }

  function subscribe(listener) {
    nextListeners.push(listener)
    return function unsubscribe() {
      const index = nextListeners.indexOf(listener)
      nextListeners.splice(index, 1)
    }
  }

  function dispatch(action) {
    currentState = currentReducer(currentState, action)
    const listeners = (currentListeners = nextListeners)
    for (let i = 0; i < listeners.length; i++) {
      const listener = listeners[i]
      listener()
    }
    return action
  }

  dispatch({ type: ActionTypes.INIT })

  return {
    dispatch,
    subscribe,
    getState,
  }
}

```

结合 store.js 中的 createStore 来看，不考虑插件情况 composeEnhancers 即为 compose

``` js
const store = createStore(rootReducer, compose(
  applyMiddleware(thunk),
));
```

不考虑插件 composeEnhancers 即为 compose，其中
1. rootReducer 对应 reducer
2. compose(applyMiddleware(thunk)) 对应 preloadedState
3. enhancer 是 undefined

最后执行的是

``` js
enhancer(createStore)(reducer, preloadedState)
```

即执行下方，其中 preloadedState 为 undefined，并且 createStore 被作为参数传入

``` js
(compose(applyMiddleware(thunk))(createStore))(reducer, preloadedState)
```

### compose

看起来是相当复杂的，我们一步步来看，首先是看下 compose 它的作用

``` js

// 来源 redux 中的 compose.js
export default function compose(...funcs) {
  if (funcs.length === 0) {
    return arg => arg
  }

  if (funcs.length === 1) {
    return funcs[0]
  }

  return funcs.reduce((a, b) => (...args) => a(b(...args)))
}

```
代码很简洁，可以看出主要用于多个函数的合并操作，按照 funcs 的顺序从右向左做合并，其中 b 接受到参数 args 后运行的结果作为 a 的参数，a 的运行参数作为 a 左边函数的参数，这样将 funcs 遍历一遍，用一个栗子来看看

``` js
function add (a) {  
  return function (b) {    
    return a + b
  }
}
// 得到合成后的方法
const add6 = compose(add(1), add(2), add(3))
add6(10) // 16 相当于 compose(add(1), add(2), add(3))(10)

```
这时，10 相当于 args 被传入最右边的 add(3)，即执行 add(3)(10) 后结果是 13，13 作为 add(2) 的参数即执行 add(2)(13) 结果是 15，最后执行 add(1)(15)，最后的结果16

回过头来再来看看之前的案例

``` js

(compose(applyMiddleware(thunk))(createStore))(reducer, preloadedState)
就相当于
applyMiddleware(thunk)(createStore)(reducer, preloadedState)

```

### applyMiddleware

接着，我们看下 applyMiddleware 的原理，其中 middlewares 对应 thunk，当然也可以传多个中间件，这里我们只使用了一个， createStore对应的就是 createStore，而 args 对应着 reducer 和 preloadedState，终于对上号了

``` js

export default function applyMiddleware(...middlewares) {
  return createStore => (...args) => {
    const store = createStore(...args)
    let dispatch = () => {
      throw new Error(
        `Dispatching while constructing your middleware is not allowed. ` +
          `Other middleware would not be applied to this dispatch.`
      )
    }
    let chain = []

    const middlewareAPI = {
      getState: store.getState,
      dispatch: (...args) => dispatch(...args)
    }
    chain = middlewares.map(middleware => middleware(middlewareAPI))
    dispatch = compose(...chain)(store.dispatch)

    return {
      ...store,
      dispatch
    }
  }
}

```

最后的运行结果即是我们最初通过 createStore 初始化后的 store 对象，可以看到，其中的 dispatch 被重写了，是被 middleware 即我们传入的 thunk 重写了，因为 middlewares 长度为1，因此chain就只有一个元素 compose 传入的即是

``` js
middleware(middlewareAPI)
也就是
thunk(middlewareAPI)
```

### thunk

做了thunk(middlewareAPI)(store.dispatch)的执行后，得到了新的dispatch，是时候来看看thunk了

```js

function createThunkMiddleware(extraArgument) {
  return ({ dispatch, getState }) => (next) => (action) => {
    if (typeof action === 'function') {
      return action(dispatch, getState, extraArgument);
    }

    return next(action);
  };
}

const thunk = createThunkMiddleware();
thunk.withExtraArgument = createThunkMiddleware;

export default thunk;

```

也是非常简洁，我们改写下，其中参数中的 dispatch 和 getState 分别对应 middlewareAPI 中的 dispatch 和 getState，next 是 store.dispatch，action 即是业务逻辑中通过 dispatch(action) 提交的 action，这里返回的是函数，当业务逻辑中通过 dispatch(action) 时，action 可以是对象，也可以是函数；如果是函数，默认会把 dispatch, getState, extraArgument 传入，即可以在一个 action 中嵌套 action，如案例中的 getDishs 即是这样的一个 action，而 deleteNapkin 是一个对象 action，其他的如 placeDishsAction是没有嵌套 action 的 action，当然它也是一个函数

``` js

export default function({ dispatch, getState }) {
  
  return (next) => (action) => {
    if (typeof action === 'function') {
      return action(dispatch, getState, extraArgument);
    }

    return next(action);
  };
}
```

### combineReducers

最后，我们来看下遗漏的点就是把多个 reducer 合并进行统一管理

```js

// redux 中的 combineReducers.js

export default function combineReducers(reducers) {
  const reducerKeys = Object.keys(reducers)
  const finalReducers = {}
  for (let i = 0; i < reducerKeys.length; i++) {
    const key = reducerKeys[i]

    if (typeof reducers[key] === 'function') {
      finalReducers[key] = reducers[key]
    }
  }
  const finalReducerKeys = Object.keys(finalReducers)

  return function combination(state = {}, action) {
    let hasChanged = false
    const nextState = {}
    for (let i = 0; i < finalReducerKeys.length; i++) {
      const key = finalReducerKeys[i]
      const reducer = finalReducers[key]
      const previousStateForKey = state[key]
      const nextStateForKey = reducer(previousStateForKey, action)
      nextState[key] = nextStateForKey
      hasChanged = hasChanged || nextStateForKey !== previousStateForKey
    }
    return hasChanged ? nextState : state
  }
}

```

在 combineReducers 中，其中 reducers 就是 reducer1 和 reducer2，通过合并后存储哈希表 finalReducers 管理如下，key 为 reducer 名，func 是对应 reducer 的处理逻辑，当通过 dispatch(action) 时，会执行 combination 逻辑，遍历并执行所有的 reducer 获取最新的 state，并和之前的 state 对比以确认返回的 state

```js

const finalReducers = {
  reducer1: func1
  reducer2: func2
}

```

不过需要注意的一点是，在 createStore 的最后会执行 dispatch({ type: ActionTypes.INIT })，这一步是初始化 state 操作，因为一开始传递的 preloadedState 是 undefined，即c reateStore 中的 currentState 是 undefined，当通过 getState 获取 state 时是空的，因此需要做一次初始化操作，初始化时执行 combination 逻辑，依然是遍历每个 reducer，每个 reducer 的第一个参数 state 默认是初始化的参数 initialState，最后在 nextState 存储的将是如下结构，即通过 getState 获取的也将是这个结构

```js

const nextState = {
  reducer1: {
    tablewareCount: 1,
    teaCount: 0,
    dishs: [],
  },
  reducer2: {
    napkinCount: 1,
  }
}

```

## 总结

看到这里，对 redux 的内部实现是不是有了一些认识，如果还是有些模糊，不妨结合源码和示例在脑海里多运行几遍，希望能对你有所帮助！