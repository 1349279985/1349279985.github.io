---
title: 为什么要上Hooks的车
date: 2019-12-10 23:38:47
tags:
categories:
keywords:
---

__React Hooks__ 已发布几个月时间，在过去的几个月里笔者将其全面应用到团队的大型项目中，期间收获了不少。 __Hooks__ 相比 __Class Component__ 有多方面的优势，笔者将介绍 __Hooks__ 的各方面并针对性结合实际业务场景讲解，带你上 __Hooks__ 的车。

<div style="width:100%;margin:auto">{% asset_img 0.png %}</div>

<!-- more -->

## 前情提要

__React Hooks__  在 __React__ 的 __[16.8.0 (February 6, 2019)](https://github.com/facebook/react/blob/master/CHANGELOG.md#1680-february-6-2019)__ 版本中引进，并给 __React__ 本身带来了新的血液，发布前期它的关注度很高，大家关注它是否会替换 __React__ 的 __Class Component__，因为它看起来非常的简约，将一切函数化，这仿佛带我们走进了一个纯真的年代，一切看起来是那么的简单。__[React 团队](https://reactjs.org/docs/hooks-intro.html#gradual-adoption-strategy)__ 并不推荐在不熟悉它的前提下就接入到项目中，而是需要先了解它的特性以及编写或转化成本，使用场景在现在看来大部分都能覆盖，__React__ 团队后期会更新 __Hooks__ 以覆盖 __Class Component__ 的所有场景。推荐新的项目采用 __Hooks__，因为 __Hooks__ 相比 __Class Component__ 有多方面的优势，同时 __Hooks__ 也会越来越完善。

## 为什么我要使用Hooks

__React__ 团队在介绍 __Hooks__ 时通过一句话暗示着多年来 __Component__ 面临的问题

> Hooks solve a wide variety of seemingly unconnected problems in React that we’ve encountered over five years of writing and maintaining tens of thousands of components.

通过上面的口吻能看出，官方团队很看好 __Hooks__ 的到来，不仅如此，从 __React__ 附近的产业链也能看出，__Redux__ 在 __React Redux v7.1.0__ 版本中表达了对 __Hooks__ 的欢呼和支持，并提供 __Redux Hooks__ 摆脱过去 __connect__ 那一套，因为那一套只属于 __Class Component__，新的 [Hooks API](https://react-redux.js.org/next/api/hooks) 特性将会和 __React Hooks__ 保持一致的体验。

<div style="width:100%;margin:auto">{% asset_img 1.png %}</div>

触发我使用 __Hooks__ 最重要的导火线是官方团队分析 __Hooks__ 相比 __Class Component__ 的[多方位优势](https://reactjs.org/docs/hooks-intro.html#motivation)。

### [逻辑复用性](https://reactjs.org/docs/hooks-intro.html#its-hard-to-reuse-stateful-logic-between-components)

__Class Component__ 中如果想复用组件中的逻辑，一般采取的方式有 __[HOC](https://reactjs.org/docs/higher-order-components.html)__ 和 __[Render Props](https://reactjs.org/docs/render-props.html)__，而 __HOC__ 封装思想是对组件做统一处理如 __connect__，这种方式依然需依赖于组件并试图改变组件的处理逻辑，同时想在一个组件应用多个独立的逻辑复用，__HOC__ 难以处理；__Render Props__ 具有和 __HOC__ 类似的容器特性，多个独立的逻辑复用可能会出现嵌套地狱，让代码的维护性大大折扣。而 __Hooks__ 呢，对于解决逻辑复用性问题，它的方式很巧妙也很灵活，请尽情拥抱 __[Custom Hooks](https://reactjs.org/docs/hooks-custom.html)__，会很香。

### [组件可读性](https://reactjs.org/docs/hooks-intro.html#complex-components-become-hard-to-understand)

__Class Component__ 中，有很多的生命周期需要在意，__React16__ 中包括但不限于 __componentDidMount__、__componentDidUpdate__ 还有名字很长的 __getDerivedStateFromProps__，一方面会使 __React__ 业务的编写成本很高，另一方面每次写完组件时，生命周期流程图都需要在脑海里运行一遍以确保无误。对于编写及理解组件层面，__Hooks__ 给出了它的方式，请尽量拥抱 __[useState](https://reactjs.org/docs/hooks-state.html)__ 和 __[useEffect](https://reactjs.org/docs/hooks-effect.html)__，__Hooks__ 用独特的设计帮你缓解生命周期流程图的阴影。

__Class Component__ 中，通常业务组件会在不同生命周期维护着相同状态数据的变更，有时这会是一种浪费比如事件监听的绑定和取消，有时这不好管理因为有些状态是可以拆分成多个独立的，但又必须写在一个生命周期中。对于这几点，__Hooks__ 中 __useEffect__ 的做法是聚合生命周期以共享状态，同时可编写多个同样的 __Hook__ 以实现状态独立管理。除此之外， [Hooks](https://reactjs.org/docs/hooks-reference.html) 还有其他优秀的 __Hook__ 关注组件的性能层面，有些也是 __Class Component__ 目前无法比拟的，如 __[useMemo](https://reactjs.org/docs/hooks-reference.html#usememo)__ 关注大量计算逻辑的优化，__[useCallback](https://reactjs.org/docs/hooks-reference.html#usecallback)__ 关注父子组件事件回调的优化，__[useReducer](https://reactjs.org/docs/hooks-reference.html#usereducer)__ 减轻 __useState__ 的压力，__[useContext](https://reactjs.org/docs/hooks-reference.html#usecontext)__ 关注组件间的数据共享，__[useRef](https://reactjs.org/docs/hooks-reference.html#useref)__ 关注缓存方式的优化。

### [编写复杂性](https://reactjs.org/docs/hooks-intro.html#classes-confuse-both-people-and-machines)

__Class Component__ 中，组件和 __this__ 是离不开的包括事件绑定类 __this__ 还有状态更新类 __this__。对于事件绑定类 __this__，有多种绑定的方式，一方面可以选择构造函数中绑定，虽然能防止重复绑定的问题发生但增加了手动 __bind__ 工作量，这看起来是比较多余的；另一方面可以选择箭头函数间接绑定，但在元素上绑定会带来重复绑定问题并致使子组件重复渲染。对于这一点，__Hooks__ 采用的方案则是不使用 __this__，__this__ 的意义是指向组件实例并访问实例属性和方法，__Hooks__ 依托于 __Function Component__ 并采用闭包的形式管理 __Hook__ 中的变量， 能达到和 __Class Component__ 同样的效果，使用 __Hooks__ 反而少了份 __this__ 的担心。

## 上Hooks车前的思考

__Hooks__ 的这些特性着实让人动心，但果真要开始用 __Hooks__ 时就有点下不去手，一方面因为对 __Class Component__ 的写法很熟悉很亲切，现在马上要接触新的写法会感到不适应；另一方面对于 __Hooks__ 没有很了解，怕没有预想的那么好而且怕踩坑。

其实这些担心是多余的，官方团队对 __Hooks__ 的引入做了解释并推荐在新项目中使用，可看出 __Hooks__ 能解决现有 __Class Component__ 的大部分场景而且 __Hooks__ 让人眼前一亮的特性值得技术人去深究并运用实践。

有了这些心里支撑，下面就是按照哪种路线学习 __Hooks__，通过一段时间的使用体验，笔者推荐先了解 __Hooks__ 的设计原理并在实际的业务场景中应用 __Hooks__，对于具体的需求首先考虑 __Hooks__ 方式，熟悉了 __Hooks__ 的特性加上使用体验后再考虑要不要转化之前项目中的 __Class Component__。

对于 __Hooks__ 原理这点，推荐[中文这篇](https://github.com/brickspert/blog/issues/26)或者[英文这篇](https://medium.com/@ryardley/react-hooks-not-magic-just-arrays-cd4f1857236e)简洁易懂的原理解析能满足不同人群的喜好。对 __Hooks__ 的原理有了了解后，就能惊叹于 __Hooks__ 巧妙的设计，知道 __React Hooks__ 其实和生命周期没太大关系，__Hooks__ 有自己的一套机制，在组件的创建和消亡期间通过闭包维护各个 __Hook__ 的状态数据。

## 点餐项目Hooks实践

针对 __Hooks__ 的使用，上面有提到不建议上手就是将过去的 __Class Component__ 转为 __Hooks__ 形式，因为得考虑组件逻辑复杂度，成本可能会有点大，建议采用递进的方式进入它的世界。

笔者将 __Hooks__ 在点餐项目的实践过程分为三步，第一步从业务角度出发通过几种通用的场景完成常见 __Hooks__ 的接入。第二步从 __Hooks__ 组件本身出发通过额外的 __Hooks__ 或者自定义 __Hooks__ 优化 __Hooks__ 组件。第三步将 __Class Component__ 的生命周期和 __Hooks__ 匹配并制定转化的规则最后完成重构。

### 业务需求引入Hooks

笔者将组件业务场景总结为以下通用的4种，理论上可覆盖大部分场景，并针对不同的场景推荐对应的 __Hooks__ 搭配方案。当然方案也并不唯一，需结合具体的需求。

- 需维护简单的同步状态（__useState__）
- 需维护复杂的同步状态（__useReducer__）
- 需维护简单的异步状态（__useState__ & __useEffect__）
- 需维护复杂的异步状态（__useReducer__ & __useEffect__）

定义简单和复杂的方式其实比较简单，核心是按照组件状态数据的复杂度，暂且按照组件内需要维护的状态数据数量大于 N（N = 2）时则为复杂，小于等于 N 时则为简单，可以有自己的一个判断，这里简单的定义是便于给出对应的解决方案。

定义同步和异步的判断依据是组件内需要维护的状态数据的来源，来源于异步的方式获取如接口类数据则叫异步状态，否则是同步状态。

当然如果组件需维护的状态数据既有同步也有异步的，这种场景比较复杂，可结合自身的需要选择结合以上四种中其中的多种进行搭配；如果不需要维护任何状态数据，组件则是无状态组件。

### 简单的同步状态（useState）

__场景：需要做一个券列表，提供两个 tab 切换不同类型的券，包括可用券和不可用券。如下视觉：__

<div style="width:30%;margin:auto">{% asset_img 2.png %}</div>

__分析：如果整体页面是一个组件，需要维护的状态则是 tab 所处的位置这一个同步状态，当然还需要券的数据，这个并不需要维护，它虽然来源于接口，但是只需直接渲染即可。__

__页面结构：将需要维护的状态通过 Hooks 来管理，简单的同步状态直接用 useState 即可。__

```jsx
import React, { useState } from 'react';

/**
 * @param initialState 切换tab状态的Hook
 * @returns {*}
 */
const useToggleTab = (initialState) => {
  const [showEnableCoupon, setToggleTab] = useState(initialState);
  const toggleChangeTab = () => setToggleTab(!showEnableCoupon);
  return [showEnableCoupon, toggleChangeTab];
};

const UserCouponComponent = ({ userCouponList }) => {
  // tab 所在的位置
  const [showEnableCoupon, toggleChangeTab] = useToggleTab(true);
  // 计算总的可用优惠券数量
  const totalAvailableCouponCount = getTotalAvailableCouponCount(userCouponList);
  return (
    <div className="coupons-container">
      {/* 顶部导航 */}
      <div className="title-tabs">
        <span className={`tab ${showEnableCoupon ? 'active' : ''}`} onClick={toggleChangeTab}>
          <span className="num">{totalAvailableCouponCount}</span>张可用优惠券
        </span>
        <span className={`tab ${!showEnableCoupon ? 'active' : ''}`} onClick={toggleChangeTab}>不可用优惠券</span>
      </div>
      {/* 券列表数据 */}
      <CouponList
        type={COUPON_CLICK_TYPE.CAN_SELECT}
        couponList={userCouponList}
        couponEnabledStatus={showEnableCoupon ? COUPON_APPLY_STATUS.CAN_USE : COUPON_APPLY_STATUS.CAN_NOT_USE}
        updatePromotion={coupon => updatePromotion(coupon, userCouponList)}
      />
    </div>
  );
};
```

这里用到了一个自定义 __Hook__ __useToggleTab__，不过目前看来它只属于这个组件并不需要抽取出去，__showEnableCoupon__ 是初始化的状态，__toggleChangeTab__ 是对 __showEnableCoupon__ 进行处理的自定义逻辑，这里只做了取反操作，可以根据自身的需要编写。如果采用 __Class Component__ 实现，__this__ 的绑定是少不了的，并且 __Hooks__ 方式看起来会很简洁。

### 复杂的同步状态（useReducer）

当组件中需要维护多个同步状态时，用多个 __useState__ 来管理这些状态不免显得有些臃肿，可转化为一个 __Hook useReducer__ 统一管理。

__场景：需要做一个订单菜品的展示列表，默认只显示两个菜品，点击展开全部则展开全部菜品，并且点击较复杂菜品可弹框查看菜品详情。如下视觉：__

<div style="width:90%;margin:auto">{% asset_img 3.png %}</div>

__分析：整体菜品列表可当作一个组件处理，组件需维护3个同步状态包括是否展示全部、是否展示菜品详情弹框及弹框菜品信息。__

__页面结构：useReducer 的管理方式同 Redux，包括 state、action、reducer 还有 dispatch，组件大体框架如下。__

```jsx
// state
const initialState = Immutable.Map({
  needShowDishExtraInfoPanel: false, // 是否展示菜品详情弹框
  selectedDish: Immutable.Map({}), // 弹框中的菜品信息
  needShowAllItems: false, // 是否展示全部
});
```
```jsx
// reducer
const reducer = (state, action) => {
  switch (action.type) {
    case 'UPDATE_PANEL_GIFT_INFO': // 更新弹框中的赠品信息
      return state.merge({ selectedDish: action.payload });
    case 'TOGGLE_SHOW_DISH_PANEL': // 变更菜品详情弹框展示状态
      return state.merge({ showDishPanel: action.payload });
    case 'TOGGLE_SHOW_ALL_DISHS': // 变更展示全部状态
      return state.merge({ showAllItems: action.payload });
    default:
      return state;
  }
};
```
```jsx
// 默认展示的菜品数量
const DEFAULT_SHOW_COUNT = 2;
// 变更菜品信息弹框状态及弹框中菜品信息
const handleDetailClick = (dish, dispatch) => {
	dispatch({ type: 'TOGGLE_SHOW_DISH_PANEL', payload: true });
  dispatch({ type: 'UPDATE_PANEL_GIFT_INFO', payload: dish });
}
const DishListComponent = ({ dishList }) => {
  // reducer 数据初始化
  const [state, dispatch] = useReducer(reducer, initialState);
	// 获取是否展示全部的状态
  const showAllItems = state.get('showAllItems');
	// 获取是否展示菜品详情弹框的状态
  const showDishPanel = state.get('showDishPanel');
	// 获取弹框中的菜品详情
  const selectedDish = state.get('selectedDish');
  if (!dishList.size) return null;
  const dishListInfo = showAllItems ?  dishList : dishList.slice(0, DEFAULT_SHOW_COUNT);
  return (
    <div className="dish-list-container">
      {/* 菜品列表 */}
      { dishListInfo.map(dish => <DishItem dish={dish} handleDetailClick={(dishInfo) => handleDetailClick(dishInfo, dispatch)} />)}
      {/* 是否展示全部 */}
      { !showAllItems && <div className="tip-show-more" onClick={() => dispatch({ type: 'TOGGLE_SHOW_ALL_DISHS', payload: true })}>展开全部</div> }
      {/* 菜品详情弹框 */}
      { showDishPanel && <ExtraInfoPanel onClose={() => dispatch({ type: 'TOGGLE_SHOW_DISH_PANEL', payload: false })} dish={selectedDish} />}
    </div>
  );
};
```
__handleDetailClick__ 中通过 __dispatch__ 可改变弹框状态及弹框的内容。__useReducer__ 的管理方式非常可控，而如果采用 __Class Component__ 方式，组件全局可获取状态及随意变更状态，将带来较差的维护性及较高的复杂度。

### 简单的异步状态（useState & useEffect）

异步的状态在 __Hooks__ 里并不能像同步状态那样只使用 __useState__ 来解决，当然如果这个异步状态不需要在组件内维护，那就跟券列表例子中的券数据一样，直接渲染即可，如果券数据需要维护呢，那就不能直接渲染了。为什么？看过原理解析应该能了解，__useState__ 初始化后，被初始化的状态就有个数据，这个数据会被缓存，之后组件的重新渲染是优先取缓存的数据，而异步状态的特性就是这个状态至少会变更两次，第一次是初始化的时候，可能为空，第二次是真正的数据比如接口返回。

__所以一方面需要缓存这个异步状态，另一方面需要在异步状态变更的时候能触发缓存的状态更新。__

当然异步状态的缓存依然使用 __useState__，而更新异步状态这个时候就轮到 __useEffect__ 上场了，因为它能在组件渲染时控制一段逻辑是否会触发，判别机制是异步的状态有没有发生变化

__场景：需要做一个菜品打包盒的选择页面，选择需要打包的菜品后，计算打包盒数量并判断是否全选，点击确认外带触发打包盒的收费计算。如下视觉：__

<div style="width:60%;margin:auto">{% asset_img 4.png %}</div>

__分析：整个页面组件中，可以看到只有一个异步状态菜品列表需要维护，是否全选及外带数量都可以通过菜品列表计算得出。__

__页面结构：通过 useState 来管理异步状态，并通过 useEffect 在菜品列表数据变化时通过 setDishInfos 更新这个异步状态。__

```jsx
const PackageSelector = ({ dishList }) => {
  // 外带菜品数据初始化
  const [dishInfos, setDishInfos] = useState(dishList);
  // 更新外带菜品数据到 state
  useEffect(() => setDishInfos(dishList), [dishList]);
  // 计算是否已全选
  const allSelected = judgeIsAllSelect(dishInfos);
  // 计算外带的菜品数量
  const takeAwayCount = calcuTakeAwayCount(dishInfos);
  return (
    <div id="package-list-container">
      {/* 顶部导航 */}
      <div className="select-header">
        <div className="header-left">选择商品</div>
        <div className={`header-right${allSelected ? ' active' : ''}`} onClick={() => handleToggleSelect(setDishInfos, dishInfos)}>
          {state.get('allSelected') ? '取消全选' : '全选'}
        </div>
      </div>
      {/* 外带菜品列表 */}
      { !!dishInfos.size && <DishList dishInfos={dishInfos} handleSingleSelect={(dish) => handleSingleSelect(dispatch, state, dish)}> }
      {/* 底部导航 */}
      <div className="bottom-nav-container">
        <div className="btn btn-back" onClick={pageGoBack}>返回</div>
        <div className="btn btn-confirm" onClick={confirmTakeAway}>{`确定外带 (${takeAwayCount}份)`}</div>
      </div>
    </div>
  );
};
```
对比管理同步的状态数据，只增加了一个 __useEffect__ 更新组件内的状态，非常的轻便，如果使用 __Class Component__ 实现，需在组件中维护异步状态需通过生命周期钩子 __componnetWillReceiveProps__ 或者 __getDerivedStateFromProps__ ，复杂度将大大提升。

### 复杂的异步状态（useReducer & useEffect）

菜品列表例子中提到了 __useReducer__，如果本地需维护多个状态数据并且包括异步状态，推荐使用 __useReducer__ 来管理状态数据，并结合 __useEffect__ 触发异步状态的更新逻辑。

__场景：需要做一个赠品选择页面，选择完赠品后点确定触发试算逻辑，点加号时如果赠品有加料和做法（如甜度）则展示SPU弹框选择加料等属性，点去查看展示所选赠品弹框，如下视觉：__

<div style="width:60%;margin:auto">{% asset_img 5.png %}</div>

__分析：整个页面组件中，有多个状态需要在组件内维护包括赠品数据列表（来源接口）、是否展示SPU弹框、SPU弹框赠品信息和是否展示所选赠品弹框共 4 个状态，其中来源接口的赠品列表数据为异步状态，其他为同步状态。__

__页面结构：通过 useReducer 来管理这4个状态，并通过 useEffect 在 props 的异步状态（赠品数据）变更时更新组件的异步状态。__

```jsx
// state
const initialState = Immutable.Map({
  needShowMultiPanel: false, // 是否展示SPU选择弹框
  selectedSpuDish: Immutable.Map({}), // SPU弹框内容展示所需的赠品信息
  dishGiftInfos: Immutable.Map({}), // 原始的赠品信息
  showGiftList: false, // 是否展示所选赠品信息弹框
});
```
```jsx
// reducer
const reducer = (state, action) => {
  switch (action.type) {
    case 'UPDATE_GIFT_INFO': // 更新原始的赠品信息
      return state.merge({ dishGiftInfos: action.payload });
    case 'TOGGLE_SHOW_DISH_SELECT_PANEL': // 变更SPU选择弹框展示状态
      return state.merge({ needShowMultiPanel: action.payload });
    case 'TOGGLE_SHOW_GIFT_SELECT_PANEL': // 变更赠品信息弹框展示状态
      return state.merge({ showGiftList: action.payload });
    case 'UPDATE_PANEL_SPU_DISH': // 变更SPU弹框赠品信息
      return state.merge({ selectedSpuDish: action.selectedSpuDish });
    default:
      return state;
  }
};
```
```jsx
const DishGiftComponent = ({ dishGiftInfos }) => {
  // reducer 数据初始化
  const [state, dispatch] = useReducer(reducer, initialState);
  // 更新赠品列表数据到 reducer
  useEffect(() => updateDishGiftInfos(dispatch, dishGiftInfos), [dishGiftInfos]);
  // 从 reducer 中获取最新的赠品列表数据
  const dishGiftList = state.get('dishGiftInfos');
  // 获取已选的赠品数据
  const dishGiftGroups = getDishGiftSkuGroups(discountGroups);
  // 计算已选的赠品数量
  const giftNum = getSelectedGift(discountGroups);
  return (
    <div className="dish-buy-container">
      {/* 赠品列表 */}
      <GiftGroupsComponent dishGiftGroups={dishGiftGroups} addToCart={dish => handleMinusDish(dispatch, dish, giftInfos)} minusDish={(dish => addToCart(dispatch, dish, giftInfos)} />
      {/* 赠品信息展示弹框 */}
      {state.get('showGiftList') && <GiftDishList dishGiftList={dishGiftList} />}
      {/* SPU赠品信息展示弹框 */}
      {state.get('needShowMultiPanel') && <MultiPanel spuDish={state.get('selectedSpuDish')} addToCart={dish => handleAddDish(dispatch, dish, giftInfos)} /> }
      {/* 底部导航 */}
      {!!dishGiftGroups.size && <GiftFootComponent giftNum={giftNum} >}
    </div>
  );
};
```
对于这种比较复杂的组件状态管理，对比 __Class Component__ 的实现方式，__Hooks Reducer__ 贴近 __Redux Reducer__ 的管理策略会清晰很多，__reducer__ __state__ 的更新遵循纯函数且没有副作用；而 __Class Component__ 的方式很容易造成非常混乱的局面，维护性将大大折扣。

## Hooks组件优化

这一节介绍和性能层面相关的其他 __Hooks__ 以及可复用的自定义 __Hooks__，这是 __Class Component__ 占劣势的几方面。最后给出几条 __Hooks__ 编写的建议。

### 其他Hooks

#### useMemo

上一节介绍的 __Hooks__ 围绕的是业务实现层面，除此之外还有其他的 __Hooks__ 值得关注。其中 __useMemo__ 关注计算逻辑的重复计算优化，如券列表例子中计算 __totalAvailableCouponCount__，如果组件再次渲染时，券数据并没有变化，__getTotalAvailableCouponCount__ 依然会被计算一次，而如果券数据的量很大，会带来比较大的计算开销，__Hooks__ 中的 __useMemo__ 可以优化这一点，和 __useEffect__ 的判别机制类似，当券数据没有变化时，则 __totalAvailableCouponCount__ 用缓存的值。

```jsx
const totalAvailableCouponCount = useMemo(() => getTotalAvailableCouponCount(userCouponList), [userCouponList]);
```
#### useCallback
__useCallback__ 和 __useMemo__ 用法看起来很相像，但 __useCallback__ 的设计是考虑到子组件的重复渲染问题，针对的场景是父组件传递行列式的事件 __props__，券列表例子中 __updatePromotion__ 是可用券选中后触发的逻辑，行列式绑定带来的问题是，每一次父组件渲染时，这个事件 __props__ 的引用值会发生变化，导致子组件发生重复渲染，即使影响子组件渲染的数据没发生变化，这是一种渲染浪费。__useCallback__ 可以优化这类场景，和 __useEffect__ 及 __useMemo__ 的判别机制类似。
```jsx
const updatePromotionCall = useCallback(coupon => updatePromotion(coupon, userCouponList), [userCouponList]);

<CouponList
  type={COUPON_CLICK_TYPE.CAN_SELECT}
  couponList={userCouponList}
  couponEnabledStatus={showEnableCoupon ? COUPON_APPLY_STATUS.CAN_USE : COUPON_APPLY_STATUS.CAN_NOT_USE}
  updatePromotion={updatePromotionCall}
/>
```
#### useRef & useContext

__useRef__ 及 __useContext__ 和 __Class Component__ 中的 __ref__ 及 __context__ 类似，__useRef__ 可给 __Hooks__ 组件中的元素添加唯一标识及缓存数据，__useContext__ 可在 __Hooks__ 组件实现多组件数据共享如可将 __dispatch__ 在组件顶层通过 __useContext__ 封装，则其后代组件中都可使用 __dispatch__ 而不用通过 __props__ 层层传递。

### 自定义Hooks

自定义 __Hooks__ 给 __React Hooks__ 带来了很多可能性，__Class Component__ 想实现组件内多重的状态逻辑复用很困难，而自定义 __Hooks__ 很巧妙的设计能在组件中来去自如。

多个 __Hooks__ 组件用到的状态逻辑都可提取出来作为公共 __Hooks__，__React__ 提供的原始 __Hooks__ 如 __useState__、__useEffect__ 等其实也是公用 __Hooks__。

业务中经常会用到的逻辑如 __事件监听、定时器，表单、接口、权限__ 等都可作为复用型状态逻辑，可提取出来作为公共的 __Hooks__。

在点餐项目中目前使用最多的就是事件监听和定时器，分别来看看它们怎么封装到 __Hooks__ 中。

__场景：需要给页面A的回退打点__

```jsx
// 页面A回退事件绑定及销毁
useEffect(() => {
  window.addEventListener('popstate', popHandler);
  return () => window.removeEventListener(popHandler);
});
```
__加需求：需要监听UI模块B的滚动事件并给该模块打点__

```jsx
// 页面A回退事件绑定及销毁
useEffect(() => {
  window.addEventListener('popstate', popHandler);
  return () => window.removeEventListener(popHandler);
});
// 页面A的UI模块B滚动事件绑定及销毁
const elementRef = useRef();
useEffect(() => {
  const elementB = elementRef.current;
  elementB.addEventListener('scroll', scrollHandler);
  return () => window.removeEventListener(scrollHandler);
});
```
如果其他页面也有这种绑定及销毁监听事件的逻辑，绑定的元素、事件类型等可能不同，但都是事件监听逻辑。是不是可以对事件监听逻辑封装，根据绑定元素、事件类型等参数生成自定义 __Hook__。
```jsx
/**
 * 事件绑定 Hook
 * @param eventName 事件名如click
 * @param handler 事件处理回调
 * @param useCapture 事件是否在捕获阶段执行，默认为 false
 * @param element 绑定事件的元素，默认为 window
 */
export default function useEventListener(eventName, handler, useCapture, element = window) {
  const savedHandler = useRef();
  useEffect(() => savedHandler.current = handler, [handler]);
  useEffect(() => {
    const eventListener = event => savedHandler.current(event);
    // 绑定事件
    element.addEventListener(eventName, eventListener, useCapture);
    // 销毁事件
    return () => element.removeEventListener(eventName, eventListener, useCapture);
  }, [eventName, element, useCapture]);
}
```
通过自定义的事件 __Hooks__ 实现场景如下。
```jsx
// 页面A回退事件绑定及销毁
useEventListener('popstate', popHandler);
// 页面A的UI模块B滚动事件绑定及销毁
useEventListener(elementB, 'scroll', scrollHandler);
```
类似的自定义定时器 __Hook__ 如下
```jsx
const DEFAULT_INTERVAL_DELAY = 1000;
/**
 * 定时器 Hook
 * @param callback 定时回调
 * @param delay 延时，默认1s
 */
export default function useInterval(callback, delay = DEFAULT_INTERVAL_DELAY) {
  const savedCallback = useRef();

  useEffect(() => savedCallback.current = callback);
  useEffect(() => {
    const tick = () => savedCallback.current();
    // 监听定时器
    const id = setInterval(tick, delay);
    // 取消监听定时器
    return () => clearInterval(id);
  }, [delay]);
}
```
使用自定义定时器 __Hook__
```jsx
// 定时循环处理一段逻辑
useInterval(intervalHandler, 2000);
```
多个自定义 __Hooks__ 自由搭配
```jsx
// 定时循环处理一段逻辑
useInterval(intervalHandler, 2000);
// 页面A回退事件绑定及销毁
useEventListener('popstate', popHandler);
// 页面A的UI模块B滚动事件绑定及销毁
useEventListener(elementB, 'scroll', scrollHandler);
```
自定义 __Hooks__ 的封装，一方面代码量会减少很多；一方面不需关心 __Hooks__ 内部的处理逻辑，能大大减轻工作量；另一方面 __Hooks__ 之间相互独立，互不影响，也更具灵活性。

### Hooks编写建议

以上一方面总结了不同业务场景下 __Hooks__ 接入的推荐方案，一方面针对 __Hooks__ 组件的特定场景给出了侧重组件性能优化的 __Hooks__ 选择；另一方面介绍了相比 __Class Component__ 来说，状态逻辑复用更佳方案即自定义 __Hooks__。至此，__Hooks__ 的相关内容已基本覆盖，这一节针对 __Hooks__ 的编写给出几条笔者觉得实用的建议。

- 不建议在同一个 __Hook__ 中处理太多的状态逻辑，建议将复杂的状态拆分为多个 __Hooks__ 分别管理，一方面状态可读性更佳，逻辑更清晰；另一方面维护性更佳，便于后期抽离公共 __Hooks__
- 所有的 __Hooks__ 申明需放在组件顶部，在第一个 __Hook__ 和最后一个 __Hook__ 之间不建议使用判断或者循环逻辑，因为这会打乱 __Hooks__ 内部的索引机制，带来无法预料的问题

## Class Component转Hooks Component

对 __Hooks__ 内容有了熟悉的理解后，如果项目里的 __Class Component__ 的逻辑混乱或者可读性很差，不妨使用 __Hooks__ 重构下，效果会更好。

其实如果了解 __Class Component__ 中的生命周期，再加上 __Hooks__ 的经验累积，重构并不复杂

先来看看 __React16__ 目前推荐的[生命周期](https://zh-hans.reactjs.org/docs/react-component.html#the-component-lifecycle)

- __componentDidMount__ 组件第一次渲染后触发
- __componentDidUpdate__ 组件第N（N>1）次渲染后触发
- __getDerivedStateFromProps__ 组件每次渲染前触发
- __componentUnmount__ 组件销毁前触发
- __getSnapShotBeforeUpdate__ 组件第N（N>1）次渲染前触发
- __getDerivedStateFromError__ 子组件抛出异常后触发
- __componentDidCatch__ 子组件抛出异常后触发，未来版本将不推荐

总览后，__getSnapShotBeforeUpdate__ 在现有业务中很少用到，并且目前 __Hooks__ 还不支持 [Error Boundaries](https://zh-hans.reactjs.org/docs/react-component.html#error-boundaries) 即子组件发生错误时没法使用 __React16__ 的降级方案，除此之外采用 __Hooks__ 来模拟其他生命周期还是没问题的，即核心是基于 __useEffect__

- __componentDidMount__ 只是第一次调用。相当于 __useEffect__ 的第二个参数传空数组
- __componentDidUpdate__ 常配合 __componentDidMount__ 使用。__useEffect__ 的第二个参数传递二次渲染后的逻辑中依赖的数据
- __getDerivedStateFromProps__ 通常将异步 __props__ 缓存到 __state__ 中。配合状态存储 __Hooks__（useState 或 useReducer）和 状态更新 __Hooks__ （useEffect）管理数据
- __componentUnmount__ 组件销毁的执行。在 __useEffect__ 中返回箭头函数执行销毁前逻辑

基于以上核心规则重构，基本能满足常见的业务场景。

## 下Hooks车后的回想

__Hooks__ 相比过去的 __Class Component__ 确实有很多优势，一方面代码更加简约并且全局代码风格一致即函数化；一方面切除事件 __this__ 绑定让代码可读性更佳，让代码更加清晰；一方面去除生命周期，收敛组件的状态逻辑，管理更加可控，并且大大减轻组件复杂度；另一方面将状态复用发挥到极致，极具灵活性同时保持独立性。

以下是对这次 __Hooks__ 引入到点餐后的效果总结，包括代码可读性、逻辑复用性、组件可控性、场景覆盖度、组件性能值 5个方面。

|     |Hooks Component|Class Component|
|:----|:----|:----|
|代码可读性|`更好`。通过 __Hooks__ 管理组件复杂的状态，并且 __Hooks__ 可拆分管理，让不同的状态彼此解耦且理解更清晰|较差。通过组件全局的 __state__ 管理庞大的组件状态，状态的初始化来源于构造函数及 __props__ 致使逻辑较难理解，并且生命周期繁多，易造成较差的代码观感。|
|逻辑复用性|更好。通过自定义 __Hooks__ 可将多个组件的公共状态逻辑抽离，实现真正的逻辑复用。|`较差`。通过 __HOC__ 或者 __Render Props__ 复用状态逻辑，可能会改变组件逻辑或造成多层嵌套，组件无法完全脱离外层容器。|
|组件可控性|`更好`。通过不同的 __Hooks__ 选型可满足不同的使用场景，__useState__ 或者 __useReducer__ 状态管理方案搭配自定义状态更新逻辑让组件更加可控。|`较差`。只有一种 __state__ 更新方案即 __setState__，并且组件各状态之间无法解耦，__state__ 全局可获取易带来不可控的逻辑变更。|
|场景覆盖度|`较差`。目前业务覆盖度已基本覆盖，能满足大部分业务需求，但对于 __getSnapShotBeforeUpdate__ 以及错误边界支持度不好。|`更好`。比 __Hooks Component__ 的场景覆盖更广，有组件错误边界的降级方案。|
|组件性能值|`更好`。组件的性能方案选型更丰富，如 __React.memo__、__useMemo__ 及 __useCallBack__。|`较差`。组件的性能方案选型较少，目前有 __shouldComponentUpdate__ 和 __PureComponent__。|

综合考量，__Hooks__ 相比 __Class Component__ 的优势很大，并且也将会越来越完善，建议在新项目中使用起来。

------