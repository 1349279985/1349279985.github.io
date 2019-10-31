---
title: React查漏补缺清单
date: 2019-04-06 16:50:49
tags:
- React
- Redux
- 面试
categories: 前端
---

为了熟悉或者回顾 __React__ 及其周边的相关知识，想必这份来自 __[Github](https://github.com/sudheerj/reactjs-interview-questions/blob/master/README.md)__ 的 __React__ 自问自答面试清单会很适合你，后期我会持续对这份清单做翻译，以减轻阅读难度

<div style="width:60%;margin:auto">{% asset_img 0.png %}</div>

<!-- more -->

### React清单

| No. | Questions |
| --- | --------- |
|   | **Core React** |
|1  | [简单介绍下React?](#简单介绍下React) |
|2  | [React的主要特性有哪些?](#React的主要特性有哪些) |
|3  | [讲讲什么是JSX?](#讲讲什么是JSX) |
|4  | [React中的元素和组件有啥区别?](#React中的元素和组件有啥区别) |
|5  | [在React中咋创建组件?](#在React中咋创建组件) |
|6  | [类组件和函数组件咋做选择?](#类组件和函数组件咋做选择) |
|7  | [PureComponent是用来干啥的?](#PureComponent是用来干啥的) |
|8  | [讲讲React中的state?](#讲讲React中的state) |
|9  | [讲讲React中的props?](#讲讲React中的props) |
|10 | [state与props有啥区别?](#state与props有啥区别) |
|11 | [通过setState更新state要注意啥?](#通过setState更新state要注意啥) |
|12 | [setState中的回调是用来干啥的?](#setState中的回调是用来干啥的)
|13 | [HTML和React的事件处理有啥区别?](#HTML和React的事件处理有啥区别) |
|14 | [在JSX中咋绑定事件回调或者组件方法?](#在JSX中咋绑定事件回调或者组件方法) |
|15 | [咋给事件回调传参?](#咋给事件回调传参) |
|16 | [React中的合成事件是啥?](#React中的合成事件是啥) |
|17 | [React中的行列式条件表达式是啥?](#React中的行列式条件表达式是啥) |
|18 | [在数组中key的作用是啥?](#在数组中key的作用是啥) |
|19 | [refs是啥?](#refs是啥) |
|20 | [咋创建refs?](#咋创建refs)
|21 | [forwardRefs又是啥?](#forwardRefs又是啥) |
|22 | [CallbackRefs和findDOMNode咋选择?](#CallbackRefs和findDOMNode咋选择) |
|23 | [为什么不建议创建String类型的refs?](#为什么不建议创建String类型的refs) |
|24 | [简单介绍下虚拟DOM?](#简单介绍下虚拟DOM) |
|25 | [虚拟DOM的原理是啥?](#虚拟DOM的原理是啥) |
|26 | [Shadow DOM和Virtual DOM有啥区别?](#ShadowDOM和VirtualDOM有啥区别) |
|27 | [讲讲React Fiber?](#讲讲ReactFiber) |
|28 | [React Fiber的设计理念是啥?](#ReactFiber的设计理念是啥) |
|29 | [啥是可控组件?](#啥是可控组件) |
|30 | [啥是不可控组件?](#啥是不可控组件) |
|31 | [createElement与cloneElement有啥区别?](#createElement与cloneElement有啥区别) |
|32 | [React中state中的数据共享是啥?](#React中state中的数据共享是啥) |
|33 | [讲讲组件的生命周期?](#讲讲组件的生命周期) |
|34 | [React有哪些生命周期钩子?](#React有哪些生命周期钩子) |
|35 | [HOC是啥?](#HOC是啥) |
|36 | [在HOC组件中咋创建props代理?](#在HOC组件中咋创建props代理) |
|37 | [讲讲React中的context?](#讲讲React中的context) |
|38 | [React中的children的prop是啥?](#React中的children的prop是啥) |
|39 | [React中怎么注释代码?](#React中怎么注释代码) |
|40 | [在构造函数中使用super函数有啥作用?](#在构造函数中使用super函数有啥作用) |
|41 | [讲讲reconciliation?](#讲讲reconciliation) |
|42 | [setState中咋使用动态的key?](#setState中咋使用动态的key) |
|43 | [函数被作为props传递给组件有啥常见问题?](#函数被作为props传递给组件有啥常见问题) |
|44 | [React的lazy引入组件支持修改组件名吗?](#React的lazy引入组件支持修改组件名吗) |
|45 | [为啥React使用className而不是class属性?](#为啥React使用className而不是class属性) |
|46 | [讲讲fragments?](#讲讲fragments) |
|47 | [为啥fragments比通过div包裹要好?](#为啥fragments比通过div包裹要好) |
|48 | [React中的Portals是啥?](#React中的Portals是啥) |
|49 | [啥是无状态组件?](#啥是无状态组件) |
|50 | [啥是状态型组件?](#啥是状态型组件) |
|51 | [React中咋检查props变量类型?](#React中咋检查props变量类型) |
|52 | [React的优势有哪些?](#React的优势有哪些) |
|53 | [React有哪些劣势?](#React有哪些劣势) |
|54 | [React16中的边缘错误是做啥的](#React16中的边缘错误是做啥的) |
|55 | [React15是咋处理边缘错误的?](#React15是咋处理边缘错误的) |
|56 | [React中推荐使用哪些静态类型检查工具?](#React中推荐使用哪些静态类型检查工具) |
|57 | [ReactDOM包提供了哪些能力?](#ReactDOM包提供了哪些能力) |
|58 | [ReactDOM中的render方法是做啥的?](#ReactDOM中的render方法是做啥的) |
|59 | [ReactDOMServer是啥?](#ReactDOMServer是啥) |
|60 | [在React中咋使用innerHTML?](#在React中咋使用innerHTML) |
|61 | [在React中咋使用styles?](#在React中咋使用styles) |
|62 | [React中的事件有哪些不同?](#React中的事件有哪些不同) |
|63 | [在constructor中使用setState会发生啥?](#在constructor中使用setState会发生啥) |
|64 | [数组的index作为key会有啥影响?](#数组的index作为key会有啥影响) |
|65 | [建议在componentWillMount中使用setState吗，为啥?](#建议在componentWillMount中使用setState吗，为啥) |
|66 | [初始化的state变量中使用props会有什么影响?](#初始化的state变量中使用props会有什么影响) |
|67 | [在JSX中咋使用条件语句?](#在JSX中咋使用条件语句)
|68 | [在DOM元素上平铺props会有啥影响?](#在DOM元素上平铺props会有啥影响) |
|69 | [React中咋使用装饰器?](#React中咋使用装饰器) |
|70 | [React中咋缓存组件?](#React中咋缓存组件) |
|71 | [React中咋做服务端渲染或者SSR?](#React中咋做服务端渲染或者SSR) |
|72 | [在React中咋启用生产环境模式?](#在React中咋启用生产环境模式) |
|73 | [使用脚手架CRA构建应用有哪些好处?](#使用脚手架CRA构建应用有哪些好处) |
|74 | [在挂载阶段依次执行的生命周期是哪些?](#在挂载阶段依次执行的生命周期是哪些) |
|75 | [React16即将废弃哪些生命函数钩子?](#React16即将废弃哪些生命函数钩子) |
|76 | [函数钩子getDerivedStateFromProps的作用是啥?](#函数钩子getDerivedStateFromProps的作用是啥) |
|77 | [函数钩子getSnapshotBeforeUpdate的作用是啥?](#函数钩子getSnapshotBeforeUpdate的作用是啥) |
|78 | [Hooks会替换掉render模式或者HOC吗?](#Hooks会替换掉render模式或者HOC吗) |
|79 | [组件的命名有啥推荐方式?](#组件的命名有啥推荐方式) |
|80 | [在class组件中推荐书写函数钩子的顺序是咋样的?](#在class组件中推荐书写函数钩子的顺序是咋样的) |
|81 | [讲讲开关型组件是咋样的?](#讲讲开关型组件是咋样的) |
|82 | [为啥推荐传递函数给setState来处理state?](#为啥推荐传递函数给setState来处理state) |
|83 | [在React中咋使用严格模式?](#在React中咋使用严格模式) |
|84 | [React中的Mixins是啥?](#React中的Mixins是啥) |
|85 | [为啥isMounted是一种反模式写法?](#为啥isMounted是一种反模式写法) |
|86 | [React中支持哪些pointer事件?](#React中支持哪些pointer事件) |
|87 | [为啥React组件的首字母需要大写?](#为啥React组件的首字母需要大写) |
|88 | [React16支持自定义属性吗?](#React16支持自定义属性吗) |
|89 | [constructor和getinitialState有啥区别?](#constructor和getinitialState有啥区别) |
|90 | [咋强制渲染一个组件不需要通过setState?](#咋强制渲染一个组件不需要通过setState) |
|91 | [在React中使用super和super（props）有啥不同?](#在React中使用super和super（props）有啥不同) |
|92 | [在JSX咋使用循环?](#在JSX咋使用循环) |
|93 | [JSX的元素属性中咋拼接字符串?](#JSX的元素属性中咋拼接字符串) |
|94 | [React中的PropTypes的shape字段是啥?](#React中的PropTypes的shape字段是啥) |
|95 | [JSX中的class咋使用判断语句?](#JSX中的class咋使用判断语句) |
|96 | [React和ReactDOM有啥区别?](#React和ReactDOM有啥区别) |
|97 | [为啥ReactDOM要和React分开在两个包中?](#为啥ReactDOM要和React分开在两个包中) |
|98 | [在React中咋使用label标签?](#在React中咋使用label标签?) |
|99 | [在JSX元素style属性中咋合并多个行内样式?](#在JSX元素style属性中咋合并多个行内样式) |
|100| [当浏览器窗口大小调整时咋触发页面渲染?](#当浏览器窗口大小调整时咋触发页面渲染)
|101| [setState和replaceState有啥区别?](#setState和replaceState有啥区别) |
|102| [咋监听state的变化?](#咋监听state的变化) |
|103| [React中咋移除数组中的元素?](#React中咋移除数组中的元素) |
|104| [在render中可以不使用HTML元素吗?](#在render中可以不使用HTML元素吗) |
|105| [在React中咋优雅地打印JSON数据?](#在React中咋优雅地打印JSON数据) |
|106| [React中为啥不能修改props?](#React中为啥不能修改props) |
|107| [页面加载时咋聚焦input元素?](#页面加载时咋聚焦input元素) |
|108| [React有那几种方式更新state中的对象变量?](#React有那几种方式更新state中的对象变量) |
|109| [为啥建议传递给setState参数是函数而不是对象?](#为啥建议传递给setState参数是函数而不是对象) |
|110| [React在浏览器端运行时咋打印版本号?](#React在浏览器端运行时咋打印版本号) |
|111| [在create-react-app中有那几种方式引入polyfills?](#在create-react-app中有那几种方式引入polyfills) |
|112| [在create-react-app中咋切换http和https?](#在create-react-app中咋切换http和https) |
|113| [在create-react-app中如何避免import相对路径?](#在create-react-app中如何避免import相对路径) |
|114| [在ReactRouter中咋引入谷歌分析?](#在ReactRouter中咋引入谷歌分析) |
|115| [咋实现每秒更新组件的效果?](#咋实现每秒更新组件的效果) |
|116| [在inline样式中如何写兼容样式?](#在inline样式中如何写兼容样式) |
|117| [React和ES6咋引入和导出组件?](#React和ES6咋引入和导出组件) |
|118| [React的组件命名有哪些非硬性规定?](#React的组件命名有哪些非硬性规定) |
|119| [为啥组件的构造函数只被调用了一次?](#为啥组件的构造函数只被调用了一次) |
|120| [React中如何定义常量?](#React中如何定义常量) |
|121| [React中咋手动触发事件?](#React中咋手动触发事件) |
|122| [React中咋使用async和await?](#React中咋使用async和await) |
|123| [React项目的文件结构一般是啥样的?](#React项目的文件结构一般是啥样的) |
|124| [React动画类有哪些包?](#React动画类有哪些包) |
|125| [Styles模块的写法有哪些好处?](#Styles模块的写法有哪些好处) |
|126| [React有哪些流行的代码检查工具?](#React有哪些流行的代码检查工具) |
|127| [AJAX请求应该放在哪个生命周期?](#AJAX请求应该放在哪个生命周期) |
|128| [render的props是啥?](#render的props是啥) |
|   | **React Router** |
|129| [简单介绍下ReactRouter?](#简单介绍下ReactRouter) |
|130| [ReactRouter和history库有啥区别?](#ReactRouter和history库有啥区别) |
|131| [ReactRouter4中的<Router>有哪些组件?](#ReactRouter4中的<Router>有哪些组件) |
|132| [history库中的push和replace是干啥的?](#history库中的push和replace是干啥的) |
|133| [ReactRouter4中咋手动调用跳转?](#ReactRouter4中咋手动调用跳转) |
|134| [ReactRouter4中咋获取query](#ReactRouter4中咋获取query) |
|135| [什么时候会抛出Router可能只有一个子元素提示?](#什么时候会抛出Router可能只有一个子元素提示) |
|136| [ReactRouter4中咋传递参数到history.push中?](#ReactRouter4中咋传递参数到history.push中) |
|137| [ReactRouter4中咋添加默认或者空页面?](#ReactRouter4中咋添加默认或者空页面) |
|138| [ReactRouter4中咋获取history?](#ReactRouter4中咋获取history) |
|139| [ReactRouter4中login后咋自动重定向?](#ReactRouter4中login后咋自动重定向) |
|   | **React Redux** |
|152| [讲讲flux是啥?](#讲讲flux是啥) |
|153| [介绍下Redux是啥?](#介绍下Redux是啥) |
|154| [Redux的核心理念是啥?](#Redux的核心理念是啥) |
|155| [Redux相比flux有哪些缺点?](#Redux相比flux有哪些缺点) |
|156| [mapStateToProps和mapDispatchToProps有啥不同?](#mapStateToProps和mapDispatchToProps有啥不同) |
|157| [可以在reducer中dispatch一个action吗?](#可以在reducer中dispatch一个action吗) |
|158| [在组件外如何获取store?](#在组件外如何获取store) |
|159| [MVW模式有哪些缺点](#MVW模式有哪些缺点) |
|160| [Redux和RxJS有哪些相似之处?](#Redux和RxJS有哪些相似之处) |
|161| [页面的加载中咋dispatch一个action?](#页面的加载中咋dispatch一个action) |
|162| [咋使用connect?](#咋使用connect) |
|163| [咋重置redux中的state?](#咋重置redux中的state) |
|164| [at在connect装饰器的作用是啥?](#at在connect装饰器的作用是啥) |
|165| [React的context和Redux有啥区别?](#React的context和Redux有啥区别) |
|166| [为啥Redux中的state函数叫reducers?](#为啥Redux中的state函数叫reducers) |
|167| [在Redux中咋用AJAX?](#在Redux中咋用AJAX) |
|168| [应该把所有state都放在Redux的store中吗?](#应该把所有state都放在Redux的store中吗) |
|169| [访问Redux中store的正确方式是啥?](#访问Redux中store的正确方式是啥) |
|170| [在Redux中component和container有啥区别?](#在Redux中component和container有啥区别) |
|171| [在Redux中的constants有啥作用? ](#在Redux中的constants有啥作用) |
|172| [mapDispatchToProps有哪几种方式绑定action?](#mapDispatchToProps有哪几种方式绑定action) |
|173| [ownProps在mapStateToProps和mapDispatchToProps中的作用是啥?](#ownProps在mapStateToProps和mapDispatchToProps中的作用是啥) |
|174| [咋构建Redux的项目目录?](#咋构建Redux的项目目录) |
|175| [redux-saga是啥?](#redux-saga是啥) |
|176| [redux-saga的核心模型是啥?](#redux-saga的核心模型是啥) |
|177| [在redux-saga中call和put有啥区别](#在redux-saga中call和put有啥区别) |
|178| [redux-thunk是啥?](#redux-thunk是啥) |
|179| [redux-saga和redux-thunk有啥区别](#redux-saga和redux-thunk有啥区别) |
|180| [了解Redux调试工具吗?](#了解Redux调试工具吗) |
|181| [Redux调试工具有哪些特性?](#Redux调试工具有哪些特性) |
|182| [Redux选择器是啥?](#Redux选择器是啥) |
|183| [Redux表单是啥?](#Redux表单是啥) |
|184| [Redux表单有哪些主要特性?](#Redux表单有哪些主要特性) |
|185| [Redux中咋添加多个中间件?](#Redux中咋添加多个中间件) |
|186| [Redux中咋设置初始的state?](#Redux中咋设置初始的state) |
|187| [Redux和Relay有啥不同?](#Redux和Relay有啥不同) |
|   | **React supported libraries and Integration** |
|192| [reselect是啥?](#reselect是啥) |
|193| [了解Flow吗?](#了解Flow吗) |
|194| [Flow和PropTypes之间有啥区别?](#Flow和PropTypes之间有啥区别) |
|195| [在React中咋使用Font字体的icons?](#在React中咋使用Font字体的icons) |
|196| [简单介绍下React调试工具?](#简单介绍下React调试工具) |
|197| [本地文件为啥不会在chrome中加载调试工具?](#本地文件为啥不会在chrome中加载调试工具) |
|198| [React中咋使用Polymer?](#React中咋使用Polymer) |
|199| [React相对于Vue的优势在哪?](#React相对于Vue的优势在哪) |
|200| [React和Angular之间有啥区别?](#React和Angular之间有啥区别) |
|201| [在浏览器调试工具为啥没有React标签?](#在浏览器调试工具为啥没有React标签) |
|202| [样式型components是啥?](#样式型components是啥) |
|203| [样式型Components长啥样?](#样式型Components长啥样) |
|204| [Relay是啥?](#Relay是啥) |
|205| [在create-react-app中咋使用Typescript?](#在create-react-app中咋使用Typescript) |
|   | **Miscellaneous** |
|206| [reselect有哪些主要特性?](#reselect有哪些主要特性) |
|207| [reselect的用法是啥?](#reselect的用法是啥) |
|208| [Redux中的action长啥样的?](#Redux中的action长啥样的) |
|209| [ES6写的Class组件中能使用静态对象吗?](#ES6写的Class组件中能使用静态对象吗) |
|210| [Redux只能在React中使用吗?](#Redux只能在React中使用吗) |
|211| [使用Redux需要特殊的工具构建吗?](使用Redux需要特殊的工具构建吗) |
|212| [Redux表单咋从state中获取初始值?](#Redux表单咋从state中获取初始值) |
|213| [PropTypes中咋给prop变量设置多个类型?](#PropTypes中咋给prop变量设置多个类型) |
|214| [React中能引入SVG文件作为组件吗?](#React中能引入SVG文件作为组件吗) |
|215| [为啥不推荐写行列式或者函数式的ref?](#为啥不推荐写行列式或者函数式的ref)|
|216| [React中的渲染劫持是啥?](#React中的渲染劫持是啥)|
|217| [HOC工厂是啥?](#HOC工厂是啥)|
|218| [React组件咋传递数字?](#React组件咋传递数字?)|
|219| [我应该将所有state都放进Redux中吗，何时用组件内部的state?](#我应该将所有state都放进Redux中吗，何时用组件内部的state)|
|220| [React中的registerServerWorker是干啥的?](#React中的registerServerWorker是干啥的)|
|221| [React16中的memo是啥?](#React16中的memo是啥)|
|222| [React16中的lazy是啥?](#React16中的lazy是啥)|
|223| [通过setState咋避免不必要的更新?](#通过setState咋避免不必要的更新)|
|224| [在React16中咋渲染数组、字符和数字?](#在React16中咋渲染数组、字符和数字)|

## Core React

1. ### 简单介绍下React?

  React 是前端的一个开源库，用来构建交互式应用并在**SPA**中应用广泛。**在 web 和移动端的分层结构中，它充当展示层的角色**。React 由在 Facebook 工作的 Jordan Walke 所创建。2011年，Facebook的 News Feed 使用了它，过了一年后，它在 Instagram 也得到了应用。
  
  **[⬆ 回顶部](#React清单)**

2. ### React的主要特性有哪些?

  React 的主要特性包括:

  * 使用**虚拟DOM**来代替真实的DOM操作，以提升性能
  * 支持**服务端渲染**.
  * 遵循**单向数据流**.
  * 使用**高复用** UI 组件来构建页面
  
  **[⬆ 回顶部](#React清单)**

3. ### 讲讲什么是JSX?

  **JSX** 是一种类似于 XML 的 JS 语法扩展。React 提供有`React.createElement()`这样的语法糖来转化 JSX 语法。它的具体格式是由 JS 和 HTML 构成，看起来像模版语言。

  下面 `<h1>` 标签 通过 render 返回后，最终会由 `React.createElement()` 转化为虚拟DOM

  ```jsx
  class App extends React.Component {
    render() {
      return(
        <div>
          <h1>{'Welcome to React world!'}</h1>
        </div>
      )
    }
  }
  ```

  **[⬆ 回顶部](#React清单)**

4. ### React中的元素和组件有啥区别?

  React 中的元素是一个普通对象，它描述着屏幕上要展示的内容。而元素对象可以嵌套元素，嵌套的元素在props字段中。创建元素的方式很简单。下面是一个典型的 React 元素

  ```javascript
  const element = React.createElement(
    'div',
    {id: 'login-btn'},
    'Login'
  )
  ```

  上面的 `React.createElement()` 函数返回的对象长这样:

  ```javascript
  {
    type: 'div',
    props: {
      children: 'Login',
      id: 'login-btn'
    }
  }
  ```

  最终会通过 `ReactDOM.render()` 渲染到真实的DOM中:

  ```html
  <div id='login-btn'>Login</div>
    ```

  而组件的创建方式就很多了。可以是Class或者函数形式。通常它会有props作为变量输入，然后返回 JSX 语法树

  ```javascript
  const Button = ({ onLogin }) =>
    <div id={'login-btn'} onClick={onLogin} />
  ```

  然后 JSX 树会被 `React.createElement()` 函数转移成对象树:

  ```javascript
  const Button = ({ onLogin }) => React.createElement(
    'div',
    { id: 'login-btn', onClick: onLogin },
    'Login'
  )
  ```

  **[⬆ 回顶部](#React清单)**

5. ### 在React中咋创建组件?

  有两种方式创建组件.

  1. **函数组件:** 创建组件最简单的方式. 通常是纯函数，接收 props 作为函数的第一个参数，然后返回 React 元素

  ```jsx  
  function Greeting({ message }) {
    return <h1>{`Hello, ${message}`}</h1> 
  }
  ```

  2. **类组件:** 你也可以通过ES6形式定义组件。上面的组件可转为类组件的写法如下:

  ```jsx  
  class Greeting extends React.Component {
    render() {
      return <h1>{`Hello, ${this.props.message}`}</h1>
    }
  }
  ```

  **[⬆ 回顶部](#React清单)**

6. ### 类组件和函数组件咋做选择?

  如果函数组件内需要state或者生命周期方法则选择类组件，否则选择函数组件。而 React16 后有了 HOOKS 的支持，更推荐函数组件的写法

  **[⬆ 回顶部](#React清单)**

7. ### PureComponent是用来干啥的?

  *`React.PureComponent`* 和 *`React.Component`* 很像，除此之外，它对 `shouldComponentUpdate()` 方法做了优化。当props或者state改变时，*PureComponent* 会针对 props 和 state 做一层浅比较。而普通的*组件* 则不会做这层比较，默认 props 或 state 的变化会触发重新渲染。

  **[⬆ 回顶部](#React清单)**

8. ### 讲讲React中的state?

  组件中 *State* 是对象类型，包含着组件生命周期所需要的一些信息。我们应该尽量只在 state 中保存简单的数据，不应该将所有状态都保存在组件内，使得组件保持纯净。下面是一个存有 message 的state

  ```jsx  
  class User extends React.Component {
    constructor(props) {
      super(props)

      this.state = {
        message: 'Welcome to React world'
      }
    }

    render() {
      return (
        <div>
          <h1>{this.state.message}</h1>
        </div>
      )
    }
  }
  ```
![](state.jpg)

**[⬆ 回顶部](#React清单)**

9. ### 讲讲React中的props?

  *Props* 是组件的输入数据。它可能是一个字符串或者数字，或者是包含着很多数据的对象，它的写法就像 HTML 的标签属性一样。通常父组件给子组件传递数据时需要用到。

  它的功能如下

  1. 传递自定义的数据到子组件
  2. 传递函数，间接触发 父组件 state 的变化，使得子组件保持独立性
  3. 在子组件中可通过类似于 `this.props.reactProp` 这样的方式调用 props 上的变量

  比如创建一个有 `reactProp` 变量的 props:

  ```jsx  
  <Element reactProp={'1'} />
  ```

  `reactProp` 就成为了 Element 组件上 props 的一个属性。

  ```
  props.reactProp
  ```

  **[⬆ 回顶部](#React清单)**

10. ### state与props有啥区别?

  *props* 和 *state* 都是普通的 JS 对象，都包含着渲染相关的数据。它们的不同在于，组件的 props 就像函数的形参，组件的 state 就像函数内部的变量

  **[⬆ 回顶部](#React清单)**

11. ### 通过setState更新state要注意啥?

  如果你尝试直接修改 state 上的变量，并不会触发重新渲染

  ```javascript
  //Wrong
  this.state.message = 'Hello world'
  ```
  应该使用 `setState()` 方法更新 state

  ```javascript
  //Correct
  this.setState({ message: 'Hello World' })
  ```

  **提示:** 只能在 *constructor* 函数中直接设置 state，这是 state 初始化的地方。

  **[⬆ 回顶部](#React清单)**

12. ### setState中的回调是用来干啥的?

  当setState操作结束后且组件渲染更新后触发setState的回调函数，即在componentDidUpdate后触发。因为 `setState()` 是一步操作，因此可用于做一些后期操作。

  **提示:** 不推荐使用该回调函数，可以在生命周期方法中做更新之后的操作

  ```javascript
  setState({ name: 'John' }, () => console.log('The name has updated and component re-rendered'))
  ```

13. ### HTML和React的事件处理有啥区别?

  1. 在 HTML 中，事件名应该小写：

  ```html
  <button onclick='activateLasers()'>
  ```

  而在 React 中，遵循的是驼峰原则：

  ```jsx  
  <button onClick={activateLasers}>
  ```

  2. 在 HTML 中，可以通过 return `false` 阻止默认行为：

  ```html
  <a href='#' onclick='console.log("The link was clicked."); return false;' />
  ```

  而在 React 中，必须调用 `preventDefault()` 阻止：

  ```javascript
  function handleClick(event) {
    event.preventDefault()
    console.log('The link was clicked.')
  }
  ```

  **[⬆ 回顶部](#React清单)**

14. ### 在JSX中咋绑定事件回调或者组件方法?

  有三种方法

  1.	在类组件的构造方法中绑定。 通常的做法是在构造函数中绑定，因为这样只需要绑定一次

    ```javascript
    class Component extends React.Componenet {
      constructor(props) {
        super(props)
        this.handleClick = this.handleClick.bind(this)
      }

      handleClick() {
        // ...
      }
    }
    ```

  2. 类方法中使用箭头函数。箭头函数中的 this 指向的就是组件实例了

    ```jsx
    handleClick = () => {
      console.log('this is:', this)
    }
    ```

    ```jsx  
    <button onClick={this.handleClick}>
      {'Click me'}
    </button>
    ```

  3. 在事件回调中使用箭头函数绑定

    ```jsx  
    <button onClick={(event) => this.handleClick(event)}>
      {'Click me'}
    </button>
    ```

  **[⬆ 回顶部](#React清单)**

15. ### 咋给事件回调传参?

  可以在事件处理外包裹箭头函数，并将参数传入

  ```jsx  
  <button onClick={() => this.handleClick(id)} />
  ```

  这和 `.bind` 是等价的

  ```jsx  
  <button onClick={this.handleClick.bind(this, id)} />
  ```

  **[⬆ 回顶部](#React清单)**

16. ### React中的合成事件是啥?

    `SyntheticEvent` 是一个跨浏览器原生事件包装器。 具有与浏览器原生事件相同的接口，包括 `stopPropagation()` 和 `preventDefault()` 等, 这些事件兼容所有的浏览器。

    **[⬆ 回顶部](#React清单)**

17. ### React中的行列式条件表达式是啥?

  JS 的写法可以通过 if 语句或者是三元表达式返回需要渲染的内容，JSX中则可用大括号包裹内容并加上逻辑操作 `&&`，当然也可以使用三元表达式，而不能使用 if 语句。

  ```jsx  
  <h1>Hello!</h1>
  {
    messages.length > 0 &&
    <h2>
      You have {messages.length} unread messages.
    </h2>
  }
  ```

  **[⬆ 回顶部](#React清单)**


18. ### 在数组中key的作用是啥?

  `key` 一般用在列表渲染中给每个 item 加上唯一的标识，这样可以帮助 React 识别哪些 item 是需要更新的，或者是新加的，或者应该删除的

  ```jsx  
  const todoItems = todos.map((todo) =>
    <li key={todo.id}>
      {todo.text}
    </li>
  )
  ```

  当列表中没有唯一的ID作为 key，可以使用 index 作为最终的方案，但是有一定的风险。

  ```jsx  
  const todoItems = todos.map((todo, index) =>
    <li key={index}>
      {todo.text}
    </li>
  )
  ```

  **提示:**

  1. 不推荐在动态列表中使用 index 作为 key，可能会影响组件的渲染性能
  2. 如果 item 被单独抽取出来作为一个组件，应该将key加在这个组件上而不是里面的 li 标签上
  3. 如果不加 key，会有 console 提示

  **[⬆ 回顶部](#React清单)**

19. ### refs是啥?

  *ref* 用来获取元素实例。有时要获取DOM元素或者组件实例还是很有用的

  **[⬆ 回顶部](#React清单)**

20. ### 咋创建refs?

  有两种方法
  1. 通过 `React.createRef()` 创建实例，并将该实例挂载到元素的 `ref` 属性上。要在整个组件中使用，则在组件的构造函数创建即可
  ```jsx  
  class MyComponent extends React.Component {
    constructor(props) {
      super(props)
      this.myRef = React.createRef()
    }
    render() {
      return <div ref={this.myRef} />
    }
  }
  ```
  2. 也可以通过 ref 回调函数来创建
  ```jsx  
  class SearchBar extends Component {
      constructor(props) {
        super(props);
        this.txtSearch = null;
        this.state = { term: '' };
        this.setInputSearchRef = e => {
            this.txtSearch = e;
        }
      }
      onInputChange(event) {
        this.setState({ term: this.txtSearch.value });
      }
      render() {
        return (
            <input
              value={this.state.term}
              onChange={this.onInputChange.bind(this)}
              ref={this.setInputSearchRef} />
        );
      }
  }
  ```

  当然将箭头函数的回调放在元素上能达到同样的效果
  **提示**: 官方不推荐创建字符串类型的 ref，可能会导致一些问题

  **[⬆ 回顶部](#React清单)**

21. ### forwardRefs又是啥?

  *Ref forwarding* 可以将创建的 ref 传递到子组件，然后可以在父组件获取该 ref 绑定的元素

  ```jsx  
  const ButtonElement = React.forwardRef((props, ref) => (
    <button ref={ref} className="CustomButton">
      {props.children}
    </button>
  ));

  // Create ref to the DOM button:
  const ref = React.createRef();
  <ButtonElement ref={ref}>{'Forward Ref'}</ButtonElement>
    ```

    **[⬆ 回顶部](#React清单)**

22. ### CallbackRefs和findDOMNode咋选择?

    `findDOMNode()` 获取的是真实的DOM，而 ref 既可以获取真实 DOM，也可以

    `findDOMNode` 方式:

    ```javascript
    class MyComponent extends Component {
      componentDidMount() {
        findDOMNode(this).scrollIntoView()
      }

      render() {
        return <div />
      }
    }
    ```

    推荐的 ref 方式:

    ```javascript
    class MyComponent extends Component {
      componentDidMount() {
        this.node.scrollIntoView()
      }

      render() {
        return <div ref={node => this.node = node} />
      }
    }
    ```

    **[⬆ 回顶部](#React清单)**

23. ### 为什么不建议创建String类型的refs?

  React 中还有一个创建 ref 的方式如 `ref={'textInput'}`，通过 `this.refs.textInput` 可访问该元素。但是不建议通过这种方式创建 ref，它有下面几个问题。并且 React16 也将废弃这种方式。

  1. They *force React to keep track of currently executing component*. This is problematic because it makes react module stateful, and thus causes weird errors when react module is duplicated in the bundle.
  2. They are *not composable* — if a library puts a ref on the passed child, the user can't put another ref on it. Callback refs are perfectly composable.
  3. They *don't work with static analysis* like Flow. Flow can't guess the magic that framework does to make the string ref appear on `this.refs`, as well as its type (which could be different). Callback refs are friendlier to static analysis.
  4. It doesn't work as most people would expect with the "render callback" pattern (e.g. <DataGrid renderRow={this.renderRow} />)
      ```jsx  
      class MyComponent extends Component {
        renderRow = (index) => {
          // This won't work. Ref will get attached to DataTable rather than MyComponent:
          return <input ref={'input-' + index} />;

          // This would work though! Callback refs are awesome.
          return <input ref={input => this['input-' + index] = input} />;
        }

        render() {
          return <DataTable data={this.props.data} renderRow={this.renderRow} />
        }
      }
      ```

      **[⬆ 回顶部](#React清单)**

24. ### 简单介绍下虚拟DOM?

  虚拟DOM(VDOM)是真实DOM的一种表达方式，并且会和真实的DOM同步更新。虚拟DOM的运行机制是发生在 render 函数被调用和页面视觉发生更新之间，这个过程叫做 reconciliation 即调和阶段。

  **[⬆ 回顶部](#React清单)**

25. ### 虚拟DOM的原理是啥?

  *虚拟DOM* 的运行流程分为三步

  1. 当下面的任何数据发生变化时，对应的虚拟DOM会同步变化
      ![](vdom1.png)

  2. 接着便是 diff，对之前的虚拟DOM和最新的虚拟DOM做对比
      ![](vdom2.png)

  3. diff 完成后，只更新真实DOM中真正发生变化的部分
      ![](vdom3.png)

  **[⬆ 回顶部](#React清单)**

26. ### ShadowDOM和VirtualDOM有啥区别?

    The *Shadow DOM* is a browser technology designed primarily for scoping variables and CSS in *web components*. The *Virtual DOM* is a concept implemented by libraries in JavaScript on top of browser APIs.

    **[⬆ 回顶部](#React清单)**

27. ### 讲讲ReactFiber?

  Fiber 是 React16 中一种的新的调和机制。它的设计目的是为了解决的场景包括页面动画、布局、手势、中止及暂停能力，这些在 React16 之前可能会造成页面卡顿，并且会给这些任务分配优先级，以优化这些场景的页面体验。

  **[⬆ 回顶部](#React清单)**

28. ### ReactFiber的设计理念是啥?

  *React Fiber*的设计目的是为了解决场景包括页面动画、布局、手势的卡顿现象。它的核心思想是分片渲染，即将渲染任务分成一系列小的任务，并分配到多个帧中去执行，以充分利用空闲帧，减少卡顿。

  **[⬆ 回顶部](#React清单)**

29. ### 啥是可控组件?

  可控组件中的数据和组件的 state 挂钩，便于处理和获取

  比如下面栗子在input的输入回调中处理输入的数据，存入state中

  ```javascript
  handleChange(event) {
    this.setState({value: event.target.value.toUpperCase()})
  }
  ```

  **[⬆ 回顶部](#React清单)**

30. ### 啥是不可控组件?

  不可控组件则需要操作原生DOM才可获取元素的数据，通过会绑定ref获取原生DOM。

  下面的栗子中, 获取input中的值是通过ref来获取，和可控组件通过state方式不同

  ```jsx  
  class UserProfile extends React.Component {
    constructor(props) {
      super(props)
      this.handleSubmit = this.handleSubmit.bind(this)
      this.input = React.createRef()
    }

    handleSubmit(event) {
      alert('A name was submitted: ' + this.input.current.value)
      event.preventDefault()
    }

    render() {
      return (
        <form onSubmit={this.handleSubmit}>
          <label>
            {'Name:'}
            <input type="text" ref={this.input} />
          </label>
          <input type="submit" value="Submit" />
        </form>
      );
    }
  }
  ```

  大多数情况下，建议通过可控组件来获取表单类的数据

  **[⬆ 回顶部](#React清单)**

31. ### createElement与cloneElement有啥区别?

    JSX elements will be transpiled to `React.createElement()` functions to create React elements which are going to be used for the object representation of UI. Whereas `cloneElement` is used to clone an element and pass it new props.

    **[⬆ 回顶部](#React清单)**

32. ### React中state中的数据共享是啥?

    When several components need to share the same changing data then it is recommended to *lift the shared state up* to their closest common ancestor. That means if two child components share the same data from its parent, then move the state to parent instead of maintaining local state in both of the child components.

    **[⬆ 回顶部](#React清单)**

33. ### 讲讲组件的生命周期?

    There are four different phases of component lifecycle.

    1. **Initialization:** In this phase component prepares setting up the initial state and default props.

    2. **Mounting:** The component is ready to mount in the browser DOM. This phase covers `componentWillMount()` and `componentDidMount()` lifecycle methods.

    3. **Updating:** In this phase, the component get updated in two ways, sending the new props and updating the state. This phase covers `shouldComponentUpdate()`, `componentWillUpdate()` and `componentDidUpdate()` lifecycle methods.

    4. **Unmounting:** In this last phase, the component is not needed and get unmounted from the browser DOM. This phase includes `componentWillUnmount()` lifecycle method.
        ![](phases.png)

    **[⬆ 回顶部](#React清单)**
    <!-- TODO: new lifecycle methods in React v16 -->

34. ### React有哪些生命周期钩子?

    - **componentWillMount:** Executed before rendering and is used for App level configuration in your root component.
    - **componentDidMount:** Executed after first rendering and here all AJAX requests, DOM or state updates, and set up event listeners should occur.
    - **componentWillReceiveProps:** Executed when particular prop updates to trigger state transitions.
    - **shouldComponentUpdate:** Determines if the component will be updated or not. By default it returns true. If you are sure that the component doesn't need to render after state or props are updated, you can return false value. It is a great place to improve performance as it allows you to prevent a re-render if component receives new prop.
    - **componentWillUpdate:** Executed before re-rendering the component when there are props & state changes confirmed by `shouldComponentUpdate()` which returns true.
    - **componentDidUpdate:** Mostly it is used to update the DOM in response to prop or state changes.
    - **componentWillUnmount:** It will be used to cancel any outgoing network requests, or remove all event listeners associated with the component.

    <!-- TODO: new lifecycle methods in React v16 -->
    **[⬆ 回顶部](#React清单)**

35. ### HOC是啥?

    A *higher-order component* (*HOC*) is a function that takes a component and returns a new component. Basically, it's a pattern that is derived from React's compositional nature.

    We call them **pure components** because they can accept any dynamically provided child component but they won't modify or copy any behavior from their input components.

    ```javascript
    const EnhancedComponent = higherOrderComponent(WrappedComponent)
    ```

    HOC can be used for many use cases:

    1. Code reuse, logic and bootstrap abstraction.
    2. Render hijacking.
    3. State abstraction and manipulation.
    4. Props manipulation.

    **[⬆ 回顶部](#React清单)**

36. ### 在HOC组件中咋创建props代理?

    You can add/edit props passed to the component using *props proxy* pattern like this:

    ```jsx  
    function HOC(WrappedComponent) {
      return class Test extends Component {
        render() {
          const newProps = {
            title: 'New Header',
            footer: false,
            showFeatureX: false,
            showFeatureY: true
          }

          return <WrappedComponent {...this.props} {...newProps} />
        }
      }
    }
    ```

    **[⬆ 回顶部](#React清单)**

37. ### 讲讲React中的context?

    *Context* provides a way to pass data through the component tree without having to pass props down manually at every level. For example, authenticated user, locale preference, UI theme need to be accessed in the application by many components.

    ```javascript
    const {Provider, Consumer} = React.createContext(defaultValue)
    ```

    **[⬆ 回顶部](#React清单)**

38. ### React中的children的prop是啥?

    *Children* is a prop (`this.prop.children`) that allow you to pass components as data to other components, just like any other prop you use. Component tree put between component's opening and closing tag will be passed to that component as `children` prop.

    There are a number of methods available in the React API to work with this prop. These include `React.Children.map`, `React.Children.forEach`, `React.Children.count`, `React.Children.only`, `React.Children.toArray`.
    A simple usage of children prop looks as below,

    ```jsx  
    const MyDiv = React.createClass({
      render: function() {
        return <div>{this.props.children}</div>
      }
    })

    ReactDOM.render(
      <MyDiv>
        <span>{'Hello'}</span>
        <span>{'World'}</span>
      </MyDiv>,
      node
    )
    ```

    **[⬆ 回顶部](#React清单)**

39. ### React中怎么注释代码?

    The comments in React/JSX are similar to JavaScript Multiline comments but are wrapped in curly braces.

    **Single-line comments:**

    ```jsx  
    <div>
      {/* Single-line comments(In vanilla JavaScript, the single-line comments are represented by double slash(//)) */}
      {`Welcome ${user}, let's play React`}
    </div>
    ```

    **Multi-line comments:**

    ```jsx  
    <div>
      {/* Multi-line comments for more than
       one line */}
      {`Welcome ${user}, let's play React`}
    </div>
    ```

    **[⬆ 回顶部](#React清单)**

40. ### 在构造函数中使用super(props)有啥作用?

    A child class constructor cannot make use of `this` reference until `super()` method has been called. The same applies for ES6 sub-classes as well. The main reason of passing props parameter to `super()` call is to access `this.props` in your child constructors.

    **Passing props:**

    ```javascript
    class MyComponent extends React.Component {
      constructor(props) {
        super(props)

        console.log(this.props) // prints { name: 'John', age: 42 }
      }
    }
    ```

    **Not passing props:**

    ```javascript
    class MyComponent extends React.Component {
      constructor(props) {
        super()

        console.log(this.props) // prints undefined

        // but props parameter is still available
        console.log(props) // prints { name: 'John', age: 42 }
      }

      render() {
        // no difference outside constructor
        console.log(this.props) // prints { name: 'John', age: 42 }
      }
    }
    ```

    The above code snippets reveals that `this.props` is different only within the constructor. It would be the same outside the constructor.

    **[⬆ 回顶部](#React清单)**

41. ### 讲讲reconciliation?

    When a component's props or state change, React decides whether an actual DOM update is necessary by comparing the newly returned element with the previously rendered one. When they are not equal, React will update the DOM. This process is called *reconciliation*.

    **[⬆ 回顶部](#React清单)**

42. ### setState中咋使用动态的key?

    If you are using ES6 or the Babel transpiler to transform your JSX code then you can accomplish this with *computed property names*.

    ```javascript
    handleInputChange(event) {
      this.setState({ [event.target.id]: event.target.value })
    }
    ```

    **[⬆ 回顶部](#React清单)**

43. ### 函数被作为props传递给组件有啥常见问题?

    You need to make sure that function is not being called while passing the function as a parameter.

    ```jsx  
    render() {
      // Wrong: handleClick is called instead of passed as a reference!
      return <button onClick={this.handleClick()}>{'Click Me'}</button>
    }
    ```

    Instead, pass the function itself without parenthesis:

    ```jsx  
    render() {
      // Correct: handleClick is passed as a reference!
      return <button onClick={this.handleClick}>{'Click Me'}</button>
    }
    ```

    **[⬆ 回顶部](#React清单)**

44. ### React的lazy引入组件支持修改组件名吗?

    It is necessary because components are not DOM elements, they are constructors. Also, in JSX lowercase tag names are referring to HTML elements, not components.

    **[⬆ 回顶部](#React清单)**

45. ### 为啥React使用className而不是class属性?

    `class` is a keyword in JavaSript, and JSX is an extension of JavaScript. That's the principal reason why React uses `className` instead of `class`. Pass a string as the `className` prop.

    ```jsx  
    render() {
      return <span className={'menu navigation-menu'}>{'Menu'}</span>
    }
    ```

    **[⬆ 回顶部](#React清单)**

46. ### 讲讲fragments?

    It's common pattern in React which is used for a component to return multiple elements. *Fragments* let you group a list of children without adding extra nodes to the DOM.

    ```jsx  
    render() {
      return (
        <React.Fragment>
          <ChildA />
          <ChildB />
          <ChildC />
        </React.Fragment>
      )
    }
    ```

    There is also a *shorter syntax*, but it's not supported in many tools:

    ```jsx  
    render() {
      return (
        <>
          <ChildA />
          <ChildB />
          <ChildC />
        </>
      )
    }
    ```

47. ### 为啥fragments比通过div包裹要好?

  1. Fragments are a bit faster and use less memory by not creating an extra DOM node. This only has a real benefit on very large and deep trees.
  2. Some CSS mechanisms like *Flexbox* and *CSS Grid* have a special parent-child relationships, and adding divs in the middle makes it hard to keep the desired layout.
  3. The DOM Inspector is less cluttered.

  **[⬆ 回顶部](#React清单)**

48. ### React中的Portals是啥?

    *Portal* is a recommended way to render children into a DOM node that exists outside the DOM hierarchy of the parent component.

    ```javascript
    ReactDOM.createPortal(child, container)
    ```

    The first argument is any renderable React child, such as an element, string, or fragment. The second argument is a DOM element.

    **[⬆ 回顶部](#React清单)**

49. ### 啥是无状态组件?

    If the behaviour is independent of its state then it can be a stateless component. You can use either a function or a class for creating stateless components. But unless you need to use a lifecycle hook in your components, you should go for function components. There are a lot of benefits if you decide to use function components here; they are easy to write, understand, and test, a little faster, and you can avoid the `this` keyword altogether.

    **[⬆ 回顶部](#React清单)**

50. ### 啥是状态型组件?

    If the behaviour of a component is dependent on the *state* of the component then it can be termed as stateful component. These *stateful components* are always *class components* and have a state that gets initialized in the `constructor`.

    ```javascript
    class App extends Component {
      constructor(props) {
        super(props)
        this.state = { count: 0 }
      }

      render() {
        // ...
      }
    }
    ```

    **[⬆ 回顶部](#React清单)**

51. ### React中咋检查props变量类型?

    When the application is running in *development mode*, React will automatically check all props that we set on components to make sure they have *correct type*. If the type is incorrect, React will generate warning messages in the console. It's disabled in *production mode* due performance impact. The mandatory props are defined with `isRequired`.

    The set of predefined prop types:

    1. `PropTypes.number`
    2. `PropTypes.string`
    3. `PropTypes.array`
    4. `PropTypes.object`
    5. `PropTypes.func`
    6. `PropTypes.node`
    7. `PropTypes.element`
    8. `PropTypes.bool`
    9. `PropTypes.symbol`
    10. `PropTypes.any`

    We can define `propTypes` for `User` component as below:

    ```jsx  
    import React from 'react'
    import PropTypes from 'prop-types'

    class User extends React.Component {
      static propTypes = {
        name: PropTypes.string.isRequired,
        age: PropTypes.number.isRequired
      }

      render() {
        return (
          <>
            <h1>{`Welcome, ${this.props.name}`}</h1>
            <h2>{`Age, ${this.props.age}`}</h2>
          </>
        )
      }
    }
    ```

    **Note:** In React v15.5 *PropTypes* were moved from `React.PropTypes` to `prop-types` library.

    **[⬆ 回顶部](#React清单)**

52. ### React的优势有哪些?

    1. Increases the application's performance with *Virtual DOM*.
    2. JSX makes code easy to read and write.
    3. It renders both on client and server side (*SSR*).
    4. Easy to integrate with frameworks (Angular, Backbone) since it is only a view library.
    5. Easy to write unit and integration tests with tools such as Jest.

    **[⬆ 回顶部](#React清单)**

53. ### React有哪些劣势?

    1. React is just a view library, not a full framework.
    2. There is a learning curve for beginners who are new to web development.
    3. Integrating React into a traditional MVC framework requires some additional configuration.
    4. The code complexity increases with inline templating and JSX.
    5. Too many smaller components leading to over engineering or boilerplate.

    **[⬆ 回顶部](#React清单)**

54. ### React16中的边缘错误是做啥的?

    *Error boundaries* are components that catch JavaScript errors anywhere in their child component tree, log those errors, and display a fallback UI instead of the component tree that crashed.

    A class component becomes an error boundary if it defines a new lifecycle method called `componentDidCatch(error, info)`:

    ```jsx  
    class ErrorBoundary extends React.Component {
      constructor(props) {
        super(props)
        this.state = { hasError: false }
      }

      componentDidCatch(error, info) {
        // Display fallback UI
        this.setState({ hasError: true })
        // You can also log the error to an error reporting service
        logErrorToMyService(error, info)
      }

      render() {
        if (this.state.hasError) {
          // You can render any custom fallback UI
          return <h1>{'Something went wrong.'}</h1>
        }
        return this.props.children
      }
    }
    ```

    After that use it as a regular component:

    ```jsx  
    <ErrorBoundary>
      <MyWidget />
    </ErrorBoundary>
    ```

    **[⬆ 回顶部](#React清单)**

55. ### React15是咋处理边缘错误的?

    React v15 provided very basic support for *error boundaries* using `unstable_handleError` method. It has been renamed to `componentDidCatch` in React v16.

    **[⬆ 回顶部](#React清单)**

56. ### React中推荐使用哪些静态类型检查工具?

    Normally we use *PropTypes library* (`React.PropTypes` moved to a `prop-types` package since React v15.5) for *type checking* in the React applications. For large code bases, it is recommended to use *static type checkers* such as Flow or TypeScript, that perform type checking at compile time and provide auto-completion features.

    **[⬆ 回顶部](#React清单)**

57. ### ReactDOM包提供了哪些能力?

    The `react-dom` package provides *DOM-specific methods* that can be used at the top level of your app. Most of the components are not required to use this module. Some of the methods of this package are:

    1. `render()`
    2. `hydrate()`
    3. `unmountComponentAtNode()`
    4. `findDOMNode()`
    5. `createPortal()`

    **[⬆ 回顶部](#React清单)**

58. ### ReactDOM中的render方法是做啥的?

    This method is used to render a React element into the DOM in the supplied container and return a reference to the component. If the React element was previously rendered into container, it will perform an update on it and only mutate the DOM as necessary to reflect the latest changes.

    ```
    ReactDOM.render(element, container[, callback])
    ```

    If the optional callback is provided, it will be executed after the component is rendered or updated.

    **[⬆ 回顶部](#React清单)**

59. ### ReactDOMServer是啥?

    The `ReactDOMServer` object enables you to render components to static markup (typically used on node server). This object is mainly used for *server-side rendering* (SSR). The following methods can be used in both the server and browser environments:

    1. `renderToString()`
    2. `renderToStaticMarkup()`

    For example, you generally run a Node-based web server like Express, Hapi, or Koa, and you call `renderToString` to render your root component to a string, which you then send as response.

    ```javascript
    // using Express
    import { renderToString } from 'react-dom/server'
    import MyPage from './MyPage'

    app.get('/', (req, res) => {
      res.write('<!DOCTYPE html><html><head><title>My Page</title></head><body>')
      res.write('<div id="content">')
      res.write(renderToString(<MyPage/>))
      res.write('</div></body></html>')
      res.end()
    })
    ```

    **[⬆ 回顶部](#React清单)**

60. ### 在React中咋使用innerHTML?

    The `dangerouslySetInnerHTML` attribute is React's replacement for using `innerHTML` in the browser DOM. Just like `innerHTML`, it is risky to use this attribute considering cross-site scripting (XSS) attacks. You just need to pass a `__html` object as key and HTML text as value.

    In this example MyComponent uses `dangerouslySetInnerHTML` attribute for setting HTML markup:

    ```jsx  
    function createMarkup() {
      return { __html: 'First &middot; Second' }
    }

    function MyComponent() {
      return <div dangerouslySetInnerHTML={createMarkup()} />
    }
    ```

    **[⬆ 回顶部](#React清单)**

61. ### 在React中咋使用styles?

    The `style` attribute accepts a JavaScript object with camelCased properties rather than a CSS string. This is consistent with the DOM style JavaScript property, is more efficient, and prevents XSS security holes.

    ```jsx  
    const divStyle = {
      color: 'blue',
      backgroundImage: 'url(' + imgUrl + ')'
    };

    function HelloWorldComponent() {
      return <div style={divStyle}>Hello World!</div>
    }
    ```

    Style keys are camelCased in order to be consistent with accessing the properties on DOM nodes in JavaScript (e.g. `node.style.backgroundImage`).

    **[⬆ 回顶部](#React清单)**

62. ### React中的事件有哪些不同?

    Handling events in React elements has some syntactic differences:

    1. React event handlers are named using camelCase, rather than lowercase.
    2. With JSX you pass a function as the event handler, rather than a string.

    **[⬆ 回顶部](#React清单)**

63. ### 在constructor中使用setState会发生啥?

    When you use `setState()`, then apart from assigning to the object state React also re-renders the component and all its children. You would get error like this: *Can only update a mounted or mounting component.* So we need to use `this.state` to initialize variables inside constructor.

    **[⬆ 回顶部](#React清单)**

64. ### 数组的index作为key会有啥影响?

    Keys should be stable, predictable, and unique so that React can keep track of elements.

    In the below code snippet each element's key will be based on ordering, rather than tied to the data that is being represented. This limits the optimizations that React can do.

    ```jsx  
    {todos.map((todo, index) =>
      <Todo
        {...todo}
        key={index}
      />
    )}
    ```

    If you use element data for unique key, assuming todo.id is unique to this list and stable, React would be able to reorder elements without needing to reevaluate them as much.

    ```jsx  
    {todos.map((todo) =>
      <Todo {...todo}
        key={todo.id} />
    )}
    ```

    **[⬆ 回顶部](#React清单)**

65. ### 建议在componentWillMount中使用setState吗，为啥?

    It is recommended to avoid async initialization in `componentWillMount()` lifecycle method. `componentWillMount()` is invoked immediately before mounting occurs. It is called before `render()`, therefore setting state in this method will not trigger a re-render. Avoid introducing any side-effects or subscriptions in this method. We need to make sure async calls for component initialization happened in `componentDidMount()` instead of `componentWillMount()`.

    ```jsx  
    componentDidMount() {
      axios.get(`api/todos`)
        .then((result) => {
          this.setState({
            messages: [...result.data]
          })
        })
    }
    ```

    **[⬆ 回顶部](#React清单)**

66. ### 初始化的state变量中使用props会有什么影响?

    If the props on the component are changed without the component being refreshed, the new prop value will never be displayed because the constructor function will never update the current state of the component. The initialization of state from props only runs when the component is first created.

    The below component won't display the updated input value:

    ```jsx  
    class MyComponent extends React.Component {
      constructor(props) {
        super(props)

        this.state = {
          records: [],
          inputValue: this.props.inputValue
        };
      }

      render() {
        return <div>{this.state.inputValue}</div>
      }
    }
    ```

    Using props inside render method will update the value:

    ```jsx  
    class MyComponent extends React.Component {
      constructor(props) {
        super(props)

        this.state = {
          record: []
        }
      }

      render() {
        return <div>{this.props.inputValue}</div>
      }
    }
    ```

    **[⬆ 回顶部](#React清单)**

67. ### 在JSX中咋使用条件语句?

    In some cases you want to render different components depending on some state. JSX does not render `false` or `undefined`, so you can use conditional *short-circuiting* to render a given part of your component only if a certain condition is true.

    ```jsx  
    const MyComponent = ({ name, address }) => (
      <div>
        <h2>{name}</h2>
        {address &&
          <p>{address}</p>
        }
      </div>
    )
    ```

    If you need an `if-else` condition then use *ternary operator*.

    ```jsx  
    const MyComponent = ({ name, address }) => (
      <div>
        <h2>{name}</h2>
        {address
          ? <p>{address}</p>
          : <p>{'Address is not available'}</p>
        }
      </div>
    )
    ```

    **[⬆ 回顶部](#React清单)**

68. ### 在DOM元素上平铺props会有啥影响?

    When we *spread props* we run into the risk of adding unknown HTML attributes, which is a bad practice. Instead we can use prop destructuring with `...rest` operator, so it will add only required props. For example,

    ```jsx  
    const ComponentA = () =>
      <ComponentB isDisplay={true} className={'componentStyle'} />

    const ComponentB = ({ isDisplay, ...domProps }) =>
      <div {...domProps}>{'ComponentB'}</div>
    ```

    **[⬆ 回顶部](#React清单)**

69. ### React中咋使用装饰器?

    You can *decorate* your *class* components, which is the same as passing the component into a function. **Decorators** are flexible and readable way of modifying component functionality.

    ```jsx  
    @setTitle('Profile')
    class Profile extends React.Component {
        //....
    }

    /*
      title is a string that will be set as a document title
      WrappedComponent is what our decorator will receive when
      put directly above a component class as seen in the example above
    */
    const setTitle = (title) => (WrappedComponent) => {
      return class extends React.Component {
        componentDidMount() {
          document.title = title
        }

        render() {
          return <WrappedComponent {...this.props} />
        }
      }
    }
    ```

    **Note:** Decorators are a feature that didn't make it into ES7, but are currently a *stage 2 proposal*.

    **[⬆ 回顶部](#React清单)**

70. ### React中咋缓存组件?

    There are memoize libraries available which can be used on function components. For example `moize` library can memoize the component in another component.

    ```jsx  
    import moize from 'moize'
    import Component from './components/Component' // this module exports a non-memoized component

    const MemoizedFoo = moize.react(Component)

    const Consumer = () => {
      <div>
        {'I will memoize the following entry:'}
        <MemoizedFoo/>
      </div>
    }
    ```

    **[⬆ 回顶部](#React清单)**

71. ### React中咋做服务端渲染或者SSR?

    React is already equipped to handle rendering on Node servers. A special version of the DOM renderer is available, which follows the same pattern as on the client side.

    ```jsx  
    import ReactDOMServer from 'react-dom/server'
    import App from './App'

    ReactDOMServer.renderToString(<App />)
    ```

    This method will output the regular HTML as a string, which can be then placed inside a page body as part of the server response. On the client side, React detects the pre-rendered content and seamlessly picks up where it left off.

    **[⬆ 回顶部](#React清单)**

72. ### 在React中咋启用生产环境模式?

    You should use Webpack's `DefinePlugin` method to set `NODE_ENV` to `production`, by which it strip out things like propType validation and extra warnings. Apart from this, if you minify the code, for example, Uglify's dead-code elimination to strip out development only code and comments, it will drastically reduce the size of your bundle.

    **[⬆ 回顶部](#React清单)**

73. ### 使用脚手架CRA构建应用有哪些好处?

    The `create-react-app` CLI tool allows you to quickly create & run React applications with no configuration step.

    Let's create Todo App using *CRA*:

    ```console
    # Installation
    $ npm install -g create-react-app

    # Create new project
    $ create-react-app todo-app
    $ cd todo-app

    # Build, test and run
    $ npm run build
    $ npm run test
    $ npm start
    ```

    **[⬆ 回顶部](#React清单)**

74. ### 在挂载阶段依次执行的生命周期是哪些?

    The lifecycle methods are called in the following order when an instance of a component is being created and inserted into the DOM.

    1. `constructor()`
    2. `static getDerivedStateFromProps()`
    3. `render()`
    4. `componentDidMount()`

    **[⬆ 回顶部](#React清单)**

75. ### React16即将废弃哪些生命函数钩子?

    The following lifecycle methods going to be unsafe coding practices and will be more problematic with async rendering.

    1. `componentWillMount()`
    2. `componentWillReceiveProps()`
    3. `componentWillUpdate()`

    Starting with React v16.3 these methods are aliased with `UNSAFE_` prefix, and the unprefixed version will be removed in React v17.

    **[⬆ 回顶部](#React清单)**

76. ### 函数钩子getDerivedStateFromProps的作用是啥?

    The new static `getDerivedStateFromProps()` lifecycle method is invoked after a component is instantiated as well as before it is re-rendered. It can return an object to update state, or `null` to indicate that the new props do not require any state updates.

    ```javascript
    class MyComponent extends React.Component {
      static getDerivedStateFromProps(props, state) {
        // ...
      }
    }
    ```

    This lifecycle method along with `componentDidUpdate()` covers all the use cases of `componentWillReceiveProps()`.

    **[⬆ 回顶部](#React清单)**

77. ### 函数钩子getSnapshotBeforeUpdate的作用是啥?

    The new `getSnapshotBeforeUpdate()` lifecycle method is called right before DOM updates. The return value from this method will be passed as the third parameter to `componentDidUpdate()`.

    ```javascript
    class MyComponent extends React.Component {
      getSnapshotBeforeUpdate(prevProps, prevState) {
        // ...
      }
    }
    ```

    This lifecycle method along with `componentDidUpdate()` covers all the use cases of `componentWillUpdate()`.

    **[⬆ 回顶部](#React清单)**

78. ### Hooks会替换掉render模式或者HOC吗?

    In JSX the React element is transpiled to `React.createElement()` which represents an UI element. Whereas `React.cloneElement()` is used in order to clone an element and pass it new props.

    **[⬆ 回顶部](#React清单)**

79. ### 组件的命名有啥推荐方式?

    It is recommended to name the component by reference instead of using `displayName`.

    Using `displayName` for naming component:

    ```javascript
    export default React.createClass({
      displayName: 'TodoApp',
      // ...
    })
    ```

    The **recommended** approach:

    ```javascript
    export default class TodoApp extends React.Component {
      // ...
    }
    ```

    **[⬆ 回顶部](#React清单)**

80. ### 在class组件中推荐书写函数钩子的顺序是咋样的?

    *Recommended* ordering of methods from *mounting* to *render stage*:

    1. `static` methods
    2. `constructor()`
    3. `getChildContext()`
    4. `componentWillMount()`
    5. `componentDidMount()`
    6. `componentWillReceiveProps()`
    7. `shouldComponentUpdate()`
    8. `componentWillUpdate()`
    9. `componentDidUpdate()`
    10. `componentWillUnmount()`
    11. click handlers or event handlers like `onClickSubmit()` or `onChangeDescription()`
    12. getter methods for render like `getSelectReason()` or `getFooterContent()`
    13. optional render methods like `renderNavigation()` or `renderProfilePicture()`
    14. `render()`

    **[⬆ 回顶部](#React清单)**

81. ### 讲讲开关型组件是咋样的?

    A *switching component* is a component that renders one of many components. We need to use object to map prop values to components.

    For example, a switching component to display different pages based on `page` prop:

    ```jsx  
    import HomePage from './HomePage'
    import AboutPage from './AboutPage'
    import ServicesPage from './ServicesPage'
    import ContactPage from './ContactPage'

    const PAGES = {
      home: HomePage,
      about: AboutPage,
      services: ServicesPage,
      contact: ContactPage
    }

    const Page = (props) => {
      const Handler = PAGES[props.page] || ContactPage

      return <Handler {...props} />
    }

    // The keys of the PAGES object can be used in the prop types to catch dev-time errors.
    Page.propTypes = {
      page: PropTypes.oneOf(Object.keys(PAGES)).isRequired
    }
    ```

    **[⬆ 回顶部](#React清单)**

82. ### 为啥推荐传递函数给setState来处理state?

    The reason behind for this is that `setState()` is an asynchronous operation. React batches state changes for performance reasons, so the state may not change immediately after `setState()` is called. That means you should not rely on the current state when calling `setState()` since you can't be sure what that state will be. The solution is to pass a function to `setState()`, with the previous state as an argument. By doing this you can avoid issues with the user getting the old state value on access due to the asynchronous nature of `setState()`.

    Let's say the initial count value is zero. After three consecutive increment operations, the value is going to be incremented only by one.

    ```javascript
    // assuming this.state.count === 0
    this.setState({ count: this.state.count + 1 })
    this.setState({ count: this.state.count + 1 })
    this.setState({ count: this.state.count + 1 })
    // this.state.count === 1, not 3
    ```

    If we pass a function to `setState()`, the count gets incremented correctly.

    ```javascript
    this.setState((prevState, props) => ({
      count: prevState.count + props.increment
    }))
    // this.state.count === 3 as expected
    ```

    **[⬆ 回顶部](#React清单)**

83. ### 在React中咋使用严格模式?

    `React.StrictMode` is an useful component for highlighting potential problems in an application. Just like `<Fragment>`, `<StrictMode>` does not render any extra DOM elements. It activates additional checks and warnings for its descendants. These checks apply for *development mode* only.

    ```jsx  
    import React from 'react'

    function ExampleApplication() {
      return (
        <div>
          <Header />
          <React.StrictMode>
            <div>
              <ComponentOne />
              <ComponentTwo />
            </div>
          </React.StrictMode>
          <Footer />
        </div>
      )
    }
    ```

    In the example above, the *strict mode* checks apply to `<ComponentOne>` and `<ComponentTwo>` components only. `<StrictMode>` currently helps with:

    1. Identifying components with **unsafe lifecycle methods**.
    2. Warning about **legacy string ref** API usage.
    3. Detecting unexpected **side effects**.
    4. Detecting **legacy context** API.

    **[⬆ 回顶部](#React清单)**

84. ### React中的Mixins是啥?

    *Mixins* are a way to totally separate components to have a common functionality. Mixins are **should not be used** and can be replaced with *higher-order components* or *decorators*.

    One of the most commonly used mixins is `PureRenderMixin`. You might be using it in some components to prevent unnecessary re-renders when the props and state are shallowly equal to the previous props and state:

    ```javascript
    const PureRenderMixin = require('react-addons-pure-render-mixin')

    const Button = React.createClass({
      mixins: [PureRenderMixin],
      // ...
    })
    ````

    **[⬆ 回顶部](#React清单)**

    <!-- TODO: mixins are deprecated -->
    

85. ### 为啥isMounted是一种反模式写法?

    The primary use case for `isMounted()` is to avoid calling `setState()` after a component has been unmounted, because it will emit a warning.

    ```javascript
    if (this.isMounted()) {
      this.setState({...})
    }
    ```

    Checking `isMounted()` before calling `setState()` does eliminate the warning, but it also defeats the purpose of the warning. Using `isMounted()` is a code smell because the only reason you would check is because you think you might be holding a reference after the component has unmounted.

    An optimal solution would be to find places where `setState()` might be called after a component has unmounted, and fix them. Such situations most commonly occur due to callbacks, when a component is waiting for some data and gets unmounted before the data arrives. Ideally, any callbacks should be canceled in `componentWillUnmount()`, prior to unmounting.

    **[⬆ 回顶部](#React清单)**

86. ### React中支持哪些pointer事件?

    *Pointer Events* provide a unified way of handling all input events. In the olden days we have a mouse and respective event listeners to handle them but nowadays we have many devices which don't correlate to having a mouse, like phones with touch surface or pens. We need to remember that these events will only work in browsers that support the *Pointer Events* specification.

    The following event types are now available in *React DOM*:

    1. `onPointerDown`
    2. `onPointerMove`
    3. `onPointerUp`
    4. `onPointerCancel`
    5. `onGotPointerCapture`
    6. `onLostPointerCaptur`
    7. `onPointerEnter`
    8. `onPointerLeave`
    9. `onPointerOver`
    10. `onPointerOut`

    **[⬆ 回顶部](#React清单)**

87. ### 为啥React组件的首字母需要大写?

    If you are rendering your component using JSX, the name of that component has to begin with a capital letter otherwise React will throw an error as unrecognized tag. This convention is because only HTML elements and SVG tags can begin with a lowercase letter.

    You can define component class which name starts with lowercase letter, but when it's imported it should have capital letter. Here lowercase is fine:

    ```jsx  
    class myComponent extends Component {
      render() {
        return <div />
      }
    }

    export default myComponent
    ```

    While when imported in another file it should start with capital letter:

    ```jsx  
    import MyComponent from './MyComponent'
    ```

    **[⬆ 回顶部](#React清单)**

88. ### React16支持自定义属性吗?

    Yes. In the past, React used to ignore unknown DOM attributes. If you wrote JSX with an attribute that React doesn't recognize, React would just skip it. For example, this:

    ```jsx  
    <div mycustomattribute={'something'} />
    ```

    Would render an empty div to the DOM with React v15:

    ```html
    <div />
    ```

    In React v16 any unknown attributes will end up in the DOM:

    ```html
    <div mycustomattribute='something' />
    ```

    This is useful for supplying browser-specific non-standard attributes, trying new DOM APIs, and integrating with opinionated third-party libraries.

    **[⬆ 回顶部](#React清单)**

89. ### constructor和getinitialState有啥区别?

    You should initialize state in the constructor when using ES6 classes, and `getInitialState()` method when using `React.createClass()`.

    Using ES6 classes:

    ```javascript
    class MyComponent extends React.Component {
      constructor(props) {
        super(props)
        this.state = { /* initial state */ }
      }
    }
    ```

    Using `React.createClass()`:

    ```javascript
    const MyComponent = React.createClass({
      getInitialState() {
        return { /* initial state */ }
      }
    })
    ```

    **Note:** `React.createClass()` is deprecated and removed in React v16. Use plain JavaScript classes instead.

    **[⬆ 回顶部](#React清单)**

90. ### 咋强制渲染一个组件不需要通过setState?

    By default, when your component's state or props change, your component will re-render. If your `render()` method depends on some other data, you can tell React that the component needs re-rendering by calling `forceUpdate()`.

    ```javascript
    component.forceUpdate(callback)
    ```

    It is recommended to avoid all uses of `forceUpdate()` and only read from `this.props` and `this.state` in `render()`.

    **[⬆ 回顶部](#React清单)**

91. ### 在React中使用super和super（props）有啥不同?

    When you want to access `this.props` in `constructor()` then you should pass props to `super()` method.

    Using `super(props)`:

    ```javascript
    class MyComponent extends React.Component {
      constructor(props) {
        super(props)
        console.log(this.props) // { name: 'John', ... }
      }
    }
    ```

    Using `super()`:

    ```javascript
    class MyComponent extends React.Component {
      constructor(props) {
        super()
        console.log(this.props) // undefined
      }
    }
    ```

    Outside `constructor()` both will display same value for `this.props`.

    **[⬆ 回顶部](#React清单)**

92. ### 在JSX咋使用循环?

    You can simply use `Array.prototype.map` with ES6 *arrow function* syntax. For example, the `items` array of objects is mapped into an array of components:

    ```jsx  
    <tbody>
      {items.map(item => <SomeComponent key={item.id} name={item.name} />)}
    </tbody>
    ```

    You can't iterate using `for` loop:

    ```jsx  
    <tbody>
      for (let i = 0; i < items.length; i++) {
        <SomeComponent key={items[i].id} name={items[i].name} />
      }
    </tbody>
    ```

    This is because JSX tags are transpiled into *function calls*, and you can't use statements inside expressions. This may change thanks to `do` expressions which are *stage 1 proposal*.

    **[⬆ 回顶部](#React清单)**

93. ### JSX的元素属性中咋拼接字符串?

    React (or JSX) doesn't support variable interpolation inside an attribute value. The below representation won't work:

    ```jsx  
    <img className='image' src='images/{this.props.image}' />
    ```

    But you can put any JS expression inside curly braces as the entire attribute value. So the below expression works:

    ```jsx  
    <img className='image' src={'images/' + this.props.image} />
    ```

    Using *template strings* will also work:

    ```jsx  
    <img className='image' src={`images/${this.props.image}`} />
    ```

    **[⬆ 回顶部](#React清单)**

94. ### React中的PropTypes的shape字段是啥?

    If you want to pass an array of objects to a component with a particular shape then use `React.PropTypes.shape()` as an argument to `React.PropTypes.arrayOf()`.

    ```javascript
    ReactComponent.propTypes = {
      arrayWithShape: React.PropTypes.arrayOf(React.PropTypes.shape({
        color: React.PropTypes.string.isRequired,
        fontSize: React.PropTypes.number.isRequired
      })).isRequired
    }
    ```

    **[⬆ 回顶部](#React清单)**

95. ### JSX中的class咋使用判断语句?

    You shouldn't use curly braces inside quotes because it is going to be evaluated as a string.

    ```jsx  
    <div className="btn-panel {this.props.visible ? 'show' : 'hidden'}">
    ```

    Instead you need to move curly braces outside (don't forget to include spaces between class names):

    ```jsx  
    <div className={'btn-panel ' + (this.props.visible ? 'show' : 'hidden')}>
    ```

    *Template strings* will also work:

    ```jsx  
    <div className={`btn-panel ${this.props.visible ? 'show' : 'hidden'}`}>
    ```

    **[⬆ 回顶部](#React清单)**

96. ### React和ReactDOM有啥区别?

    The `react` package contains `React.createElement()`, `React.Component`, `React.Children`, and other helpers related to elements and component classes. You can think of these as the isomorphic or universal helpers that you need to build components. The `react-dom` package contains `ReactDOM.render()`, and in `react-dom/server` we have *server-side rendering* support with `ReactDOMServer.renderToString()` and `ReactDOMServer.renderToStaticMarkup()`.

    **[⬆ 回顶部](#React清单)**

97. ### 为啥ReactDOM要和React分开在两个包中?

    The React team worked on extracting all DOM-related features into a separate library called *ReactDOM*. React v0.14 is the first release in which the libraries are split. By looking at some of the packages, `react-native`, `react-art`, `react-canvas`, and `react-three`, it has become clear that the beauty and essence of React has nothing to do with browsers or the DOM. To build more environments that React can render to, React team planned to split the main React package into two: `react` and `react-dom`. This paves the way to writing components that can be shared between the web version of React and React Native.

    **[⬆ 回顶部](#React清单)**

98. ### 在React中咋使用label标签?

    If you try to render a `<label>` element bound to a text input using the standard `for` attribute, then it produces HTML missing that attribute and prints a warning to the console.

    ```jsx  
    <label for={'user'}>{'User'}</label>
    <input type={'text'} id={'user'} />
    ```

    Since `for` is a reserved keyword in JavaScript, use `htmlFor` instead.

    ```jsx  
    <label htmlFor={'user'}>{'User'}</label>
    <input type={'text'} id={'user'} />
    ```

    **[⬆ 回顶部](#React清单)**

99. ### 在JSX元素style属性中咋合并多个行内样式?

    You can use *spread operator* in regular React:

    ```jsx  
     <button style={{...styles.panel.button, ...styles.panel.submitButton}}>{'Submit'}</button>
    ```

    If you're using React Native then you can use the array notation:

    ```jsx  
    <button style={[styles.panel.button, styles.panel.submitButton]}>{'Submit'}</button>
    ```

    **[⬆ 回顶部](#React清单)**

100. ### 当浏览器窗口大小调整时咋触发页面渲染?

     You can listen to the `resize` event in `componentDidMount()` and then update the dimensions (`width` and `height`). You should remove the listener in `componentWillUnmount()` method.

     ```javascript
     class WindowDimensions extends React.Component {
       componentWillMount() {
         this.updateDimensions()
       }

       componentDidMount() {
         window.addEventListener('resize', this.updateDimensions)
       }

       componentWillUnmount() {
         window.removeEventListener('resize', this.updateDimensions)
       }

       updateDimensions() {
         this.setState({width: $(window).width(), height: $(window).height()})
       }

       render() {
         return <span>{this.state.width} x {this.state.height}</span>
       }
     }
     ```

     **[⬆ 回顶部](#React清单)**

101. ### setState和replaceState有啥区别?

     When you use `setState()` the current and previous states are merged. `replaceState()` throws out the current state, and replaces it with only what you provide. Usually `setState()` is used unless you really need to remove all previous keys for some reason. You can also set state to `false`/`null` in `setState()` instead of using `replaceState()`.

     **[⬆ 回顶部](#React清单)**

102. ### 咋监听state的变化?

     The following lifecycle methods will be called when state changes. You can compare provided state and props values with current state and props to determine if something meaningful changed.

     ```jsx  
     componentWillUpdate(object nextProps, object nextState)
     componentDidUpdate(object prevProps, object prevState)
     ```

     **[⬆ 回顶部](#React清单)**

103. ### React中咋移除数组中的元素?

     The better approach is to use `Array.prototype.filter()` method.

     For example, let's create a `removeItem()` method for updating the state.

     ```javascript
     removeItem(index) {
       this.setState({
         data: this.state.data.filter((item, i) => i !== index)
       })
     }
     ```

     **[⬆ 回顶部](#React清单)**

104. ### 在render中可以不使用HTML元素吗?

     It is possible with latest version (>=16.2). Below are the possible options:

     ```jsx  
     render() {
       return false
     }
     ```

     ```jsx  
     render() {
       return null
     }
     ```

     ```jsx  
     render() {
       return []
     }
     ```

     ```jsx  
     render() {
       return <React.Fragment></React.Fragment>
     }
     ```

     ```jsx  
     render() {
       return <></>
     }
     ```

     Returning `undefined` won't work.

     **[⬆ 回顶部](#React清单)**

105. ### 在React中咋优雅地打印JSON数据?

     We can use `<pre>` tag so that the formatting of the `JSON.stringify()` is retained:

     ```jsx  
     const data = { name: 'John', age: 42 }

     class User extends React.Component {
       render() {
         return (
           <pre>
             {JSON.stringify(data, null, 2)}
           </pre>
         )
       }
     }

     React.render(<User />, document.getElementById('container'))
     ```

     **[⬆ 回顶部](#React清单)**

106. ### React中为啥不能修改props?

     The React philosophy is that props should be *immutable* and *top-down*. This means that a parent can send any prop values to a child, but the child can't modify received props.

     **[⬆ 回顶部](#React清单)**

107. ### 页面加载时咋聚焦input元素?

     You can do it by creating *ref* for `input` element and using it in `componentDidMount()`:

     ```jsx  
     class App extends React.Component{
       componentDidMount() {
         this.nameInput.focus()
       }

       render() {
         return (
           <div>
             <input
               defaultValue={'Won\'t focus'}
             />
             <input
               ref={(input) => this.nameInput = input}
               defaultValue={'Will focus'}
             />
           </div>
         )
       }
     }

     ReactDOM.render(<App />, document.getElementById('app'))
     ```

     **[⬆ 回顶部](#React清单)**

108. ### React有那几种方式更新state中的对象变量?

     1. **Calling `setState()` with an object to merge with state:**

         * Using `Object.assign()` to create a copy of the object:

             ```javascript
             const user = Object.assign({}, this.state.user, { age: 42 })
             this.setState({ user })
             ```

         * Using *spread operator*:

             ```javascript
             const user = { ...this.state.user, age: 42 }
             this.setState({ user })
             ```

     2. **Calling `setState()` with a function:**

         ```javascript
         this.setState(prevState => ({
           user: {
             ...prevState.user,
             age: 42
           }
         }))
         ```
    **[⬆ 回顶部](#React清单)**

109. ### 为啥建议传递给setState参数是函数而不是对象?

     React may batch multiple `setState()` calls into a single update for performance. Because `this.props` and `this.state` may be updated asynchronously, you should not rely on their values for calculating the next state.

     This counter example will fail to update as expected:

     ```javascript
     // Wrong
     this.setState({
       counter: this.state.counter + this.props.increment,
     })
     ```

     The preferred approach is to call `setState()` with function rather than object. That function will receive the previous state as the first argument, and the props at the time the update is applied as the second argument.

     ```javascript
     // Correct
     this.setState((prevState, props) => ({
       counter: prevState.counter + props.increment
     }))
     ```

     **[⬆ 回顶部](#React清单)**

110. ### React在浏览器端运行时咋打印版本号?

     You can use `React.version` to get the version.

     ```jsx  
     const REACT_VERSION = React.version

     ReactDOM.render(
       <div>{`React version: ${REACT_VERSION}`}</div>,
       document.getElementById('app')
     )
     ```

     **[⬆ 回顶部](#React清单)**

111. ### 在create-react-app中有那几种方式引入polyfills?

     1. **Manual import from `core-js`:**

         Create a file called (something like) `polyfills.js` and import it into root `index.js` file. Run `npm install core-js` or `yarn add core-js` and import your specific required features.

         ```javascript
         import 'core-js/fn/array/find'
         import 'core-js/fn/array/includes'
         import 'core-js/fn/number/is-nan'
         ```

     2. **Using Polyfill service:**

         Use the polyfill.io CDN to retrieve custom, browser-specific polyfills by adding this line to `index.html`:

         ```html
         <script src='https://cdn.polyfill.io/v2/polyfill.min.js?features=default,Array.prototype.includes'></script>
         ```

         In the above script we had to explicitly request the `Array.prototype.includes` feature as it is not included in the default feature set.
    
    **[⬆ 回顶部](#React清单)**

112. ### 在create-react-app中咋切换http和https?

     You just need to use `HTTPS=true` configuration. You can edit your `package.json` scripts section:

     ```json
     "scripts": {
       "start": "set HTTPS=true && react-scripts start"
     }
     ```

     or just run `set HTTPS=true && npm start`

     **[⬆ 回顶部](#React清单)**

113. ### 在create-react-app中如何避免import相对路径?

     Create a file called `.env` in the project root and write the import path:

     ```
     NODE_PATH=src/app
     ```

     After that restart the development server. Now you should be able to import anything inside `src/app` without relative paths.

     **[⬆ 回顶部](#React清单)**

114. ### 在ReactRouter中咋引入谷歌分析?

     Add a listener on the `history` object to record each page view:

     ```javascript
     history.listen(function (location) {
       window.ga('set', 'page', location.pathname + location.search)
       window.ga('send', 'pageview', location.pathname + location.search)
     })
     ```

     **[⬆ 回顶部](#React清单)**

115. ### 咋实现每秒更新组件的效果?

     You need to use `setInterval()` to trigger the change, but you also need to clear the timer when the component unmounts to prevent errors and memory leaks.

     ```javascript
     componentDidMount() {
       this.interval = setInterval(() => this.setState({ time: Date.now() }), 1000)
     }

     componentWillUnmount() {
       clearInterval(this.interval)
     }
     ```

     **[⬆ 回顶部](#React清单)**

116. ### 在inline样式中如何写兼容样式?

     React *does not* apply *vendor prefixes* automatically. You need to add vendor prefixes manually.

     ```jsx  
     <div style={{
       transform: 'rotate(90deg)',
       WebkitTransform: 'rotate(90deg)', // note the capital 'W' here
       msTransform: 'rotate(90deg)' // 'ms' is the only lowercase vendor prefix
     }} />
     ```

     **[⬆ 回顶部](#React清单)**

117. ### React和ES6咋引入和导出组件?

     You should use default for exporting the components

     ```jsx  
     import React from 'react'
     import User from 'user'

     export default class MyProfile extends React.Component {
       render(){
         return (
           <User type="customer">
             //...
           </User>
         )
       }
     }
     ```

     With the export specifier, the MyProfile is going to be the member and exported to this module and the same can be imported without mentioning the name in other components.

     **[⬆ 回顶部](#React清单)**

118. ### React的组件命名有哪些非硬性规定?

     In JSX, lowercase tag names are considered to be HTML tags. However, capitalized and lowercase tag names with a dot (property accessors) aren't.

     1. `<component />` compiles to `React.createElement('component')` (i.e, HTML tag)
     2. `<obj.component />` compiles to `React.createElement(obj.component)`
     3. `<Component />` compiles to `React.createElement(Component)`

     **[⬆ 回顶部](#React清单)**

119. ### 为啥组件的构造函数只被调用了一次?

     React's *reconciliation* algorithm assumes that without any information to the contrary, if a custom component appears in the same place on subsequent renders, it's the same component as before, so reuses the previous instance rather than creating a new one.

     **[⬆ 回顶部](#React清单)**

120. ### React中如何定义常量?

     You can use ES7 `static` field to define constant.

     ```javascript
     class MyComponent extends React.Component {
       static DEFAULT_PAGINATION = 10
     }
     ```

     *Static fields* are part of the *Class Fields* stage 3 proposal.

     **[⬆ 回顶部](#React清单)**

121. ### React中咋手动触发事件?

     You could use the ref prop to acquire a reference to the underlying `HTMLInputElement` object through a callback, store the reference as a class property, then use that reference to later trigger a click from your event handlers using the `HTMLElement.click` method. This can be done in two steps:

     1. Create ref in render method:

         ```jsx  
         <input ref={input => this.inputElement = input} />
         ```

     2. Apply click event in your event handler:

         ```javascript
         this.inputElement.click()
         ```

    **[⬆ 回顶部](#React清单)**

122. ### React中咋使用async和await?

     If you want to use `async`/`await` in React, you will need *Babel* and [transform-async-to-generator](https://babeljs.io/docs/en/babel-plugin-transform-async-to-generator) plugin. React Native ships with Babel and a set of transforms.

     **[⬆ 回顶部](#React清单)**

123. ### React项目的文件结构一般是啥样的?

     There are two common practices for React project file structure.

     1. **Grouping by features or routes:**

         One common way to structure projects is locate CSS, JS, and tests together, grouped by feature or route.

         ```
         common/
         ├─ Avatar.js
         ├─ Avatar.css
         ├─ APIUtils.js
         └─ APIUtils.test.js
         feed/
         ├─ index.js
         ├─ Feed.js
         ├─ Feed.css
         ├─ FeedStory.js
         ├─ FeedStory.test.js
         └─ FeedAPI.js
         profile/
         ├─ index.js
         ├─ Profile.js
         ├─ ProfileHeader.js
         ├─ ProfileHeader.css
         └─ ProfileAPI.js
         ```

     2. **Grouping by file type:**

         Another popular way to structure projects is to group similar files together.

         ```
         api/
         ├─ APIUtils.js
         ├─ APIUtils.test.js
         ├─ ProfileAPI.js
         └─ UserAPI.js
         components/
         ├─ Avatar.js
         ├─ Avatar.css
         ├─ Feed.js
         ├─ Feed.css
         ├─ FeedStory.js
         ├─ FeedStory.test.js
         ├─ Profile.js
         ├─ ProfileHeader.js
         └─ ProfileHeader.css
         ```
    
      **[⬆ 回顶部](#React清单)**

124. ### React动画类有哪些包?

     *React Transition Group* and *React Motion* are popular animation packages in React ecosystem.

     **[⬆ 回顶部](#React清单)**

125. ### Styles模块的写法有哪些好处?

     It is recommended to avoid hard coding style values in components. Any values that are likely to be used across different UI components should be extracted into their own modules.

     For example, these styles could be extracted into a separate component:

     ```javascript
     export const colors = {
       white,
       black,
       blue
     }

     export const space = [
       0,
       8,
       16,
       32,
       64
     ]
     ```

     And then imported individually in other components:

     ```javascript
     import { space, colors } from './styles'
     ```
     
     **[⬆ 回顶部](#React清单)**

126. ### React有哪些流行的代码检查工具?

     ESLint is a popular JavaScript linter. There are plugins available that analyse specific code styles. One of the most common for React is an npm package called `eslint-plugin-react`. By default, it will check a number of best practices, with rules checking things from keys in iterators to a complete set of prop types. Another popular plugin is `eslint-plugin-jsx-a11y`, which will help fix common issues with accessibility. As JSX offers slightly different syntax to regular HTML, issues with `alt` text and `tabindex`, for example, will not be picked up by regular plugins.

     **[⬆ 回顶部](#React清单)**

127. ### AJAX请求应该放在哪个生命周期?

     You can use AJAX libraries such as Axios, jQuery AJAX, and the browser built-in `fetch`. You should fetch data in the `componentDidMount()` lifecycle method. This is so you can use `setState()` to update your component when the data is retrieved.

     For example, the employees list fetched from API and set local state:

     ```jsx  
     class MyComponent extends React.Component {
       constructor(props) {
         super(props)
         this.state = {
           employees: [],
           error: null
         }
       }

       componentDidMount() {
         fetch('https://api.example.com/items')
           .then(res => res.json())
           .then(
             (result) => {
               this.setState({
                 employees: result.employees
               })
             },
             (error) => {
               this.setState({ error })
             }
           )
       }

       render() {
         const { error, employees } = this.state
         if (error) {
           return <div>Error: {error.message}</div>;
         } else {
           return (
             <ul>
               {employees.map(item => (
                 <li key={employee.name}>
                   {employee.name}-{employees.experience}
                 </li>
               ))}
             </ul>
           )
         }
       }
     }
     ```

     **[⬆ 回顶部](#React清单)**

128. ### render的props是啥?

     **Render Props** is a simple technique for sharing code between components using a prop whose value is a function. The below component uses render prop which returns a React element.

     ```jsx  
     <DataProvider render={data => (
       <h1>{`Hello ${data.target}`}</h1>
     )}/>
     ```

     Libraries such as React Router and DownShift are using this pattern.

     **[⬆ 回顶部](#React清单)**

## React Router

129. ### 简单介绍下ReactRouter?

     React Router is a powerful routing library built on top of React that helps you add new screens and flows to your application incredibly quickly, all while keeping the URL in sync with what's being displayed on the page.

     **[⬆ 回顶部](#React清单)**

130. ### ReactRouter和history库有啥区别?

     React Router is a wrapper around the `history` library which handles interaction with the browser's `window.history` with its browser and hash histories. It also provides memory history which is useful for environments that don't have global history, such as mobile app development (React Native) and unit testing with Node.

     **[⬆ 回顶部](#React清单)**

131. ### ReactRouter4中的<Router>有哪些组件?

     React Router v4 provides below 3 `<Router>` components:

     1. `<BrowserRouter>`
     2. `<HashRouter>`
     3. `<MemoryRouter>`

     The above components will create *browser*, *hash*, and *memory* history instances. React Router v4 makes the properties and methods of the `history` instance associated with your router available through the context in the `router` object.

     **[⬆ 回顶部](#React清单)**

132. ### history库中的push和replace是干啥的?

     A history instance has two methods for navigation purpose.

     1. `push()`
     2. `replace()`

     If you think of the history as an array of visited locations, `push()` will add a new location to the array and `replace()` will replace the current location in the array with the new one.

     **[⬆ 回顶部](#React清单)**

133. ### ReactRouter4中咋手动调用跳转?

     There are three different ways to achieve programmatic routing/navigation within components.

     1. **Using the `withRouter()` higher-order function:**

         The `withRouter()` higher-order function will inject the history object as a prop of the component. This object provides `push()` and `replace()` methods to avoid the usage of context.
         ```jsx  
         import { withRouter } from 'react-router-dom' // this also works with 'react-router-native'

         const Button = withRouter(({ history }) => (
           <button
             type='button'
             onClick={() => { history.push('/new-location') }}
           >
             {'Click Me!'}
           </button>
         ))
         ```

     2. **Using `<Route>` component and render props pattern:**

         The `<Route>` component passes the same props as `withRouter()`, so you will be able to access the history methods through the history prop.
         ```jsx  
         import { Route } from 'react-router-dom'

         const Button = () => (
           <Route render={({ history }) => (
             <button
               type='button'
               onClick={() => { history.push('/new-location') }}
             >
               {'Click Me!'}
             </button>
           )} />
         )
         ```

     3. **Using context:**

         This option is not recommended and treated as unstable API.
         ```jsx  
         const Button = (props, context) => (
           <button
             type='button'
             onClick={() => {
               context.history.push('/new-location')
             }}
           >
             {'Click Me!'}
           </button>
         )

         Button.contextTypes = {
           history: React.PropTypes.shape({
             push: React.PropTypes.func.isRequired
           })
         }
         ```

      **[⬆ 回顶部](#React清单)**

134. ### ReactRouter4中咋获取query?

     The ability to parse query strings was taken out of React Router v4 because there have been user requests over the years to support different implementation. So the decision has been given to users to choose the implementation they like. The recommended approach is to use query strings library.

     ```javascript
     const queryString = require('query-string');
     const parsed = queryString.parse(props.location.search);
     ```

     You can also use `URLSearchParams` if you want something native:

     ```javascript
     const params = new URLSearchParams(props.location.search)
     const foo = params.get('name')
     ```

     You should use a *polyfill* for IE11.

     **[⬆ 回顶部](#React清单)**

135. ### 什么时候会抛出Router可能只有一个子元素提示?

     You have to wrap your Route's in a `<Switch>` block because `<Switch>` is unique in that it renders a route exclusively.

     At first you need to add `Switch` to your imports:

     ```javascript
     import { Switch, Router, Route } from 'react-router'
     ```

     Then define the routes within `<Switch>` block:

     ```jsx  
     <Router>
       <Switch>
         <Route {/* ... */} />
         <Route {/* ... */} />
       </Switch>
     </Router>
     ```

     **[⬆ 回顶部](#React清单)**

136. ### ReactRouter4中咋传递参数到history.push中?

     While navigating you can pass props to the `history` object:

     ```javascript
     this.props.history.push({
       pathname: '/template',
       search: '?name=sudheer',
       state: { detail: response.data }
     })
     ```

     The `search` property is used to pass query params in `push()` method.

     **[⬆ 回顶部](#React清单)**

137. ### ReactRouter4中咋添加默认或者空页面?

     A `<Switch>` renders the first child `<Route>` that matches. A `<Route>` with no path always matches. So you just need to simply drop path attribute as below

     ```jsx  
     <Switch>
       <Route exact path="/" component={Home}/>
       <Route path="/user" component={User}/>
       <Route component={NotFound} />
     </Switch>
     ```

     **[⬆ 回顶部](#React清单)**

138. ### ReactRouter4中咋获取history?

     1. Create a module that exports a `history` object and import this module across the project.

         For example, create `history.js` file:

         ```javascript
         import { createBrowserHistory } from 'history'

         export default createBrowserHistory({
           /* pass a configuration object here if needed */
         })
         ```

     2. You should use the `<Router>` component instead of built-in routers. Imported the above `history.js` inside `index.js` file:

         ```jsx  
         import { Router } from 'react-router-dom'
         import history from './history'
         import App from './App'

         ReactDOM.render((
           <Router history={history}>
             <App />
           </Router>
         ), holder)
         ```

     3. You can also use push method of `history` object similar to built-in history object:

         ```javascript
         // some-other-file.js
         import history from './history'

         history.push('/go-here')
         ```

    **[⬆ 回顶部](#React清单)**

139. ### ReactRouter4中login后咋自动重定向?

     The `react-router` package provides `<Redirect>` component in React Router. Rendering a `<Redirect>` will navigate to a new location. Like server-side redirects, the new location will override the current location in the history stack.

     ```javascript
     import React, { Component } from 'react'
     import { Redirect } from 'react-router'

     export default class LoginComponent extends Component {
       render() {
         if (this.state.isLoggedIn === true) {
           return <Redirect to="/your/redirect/page" />
         } else {
           return <div>{'Login Please'}</div>
         }
       }
     }
     ```

     **[⬆ 回顶部](#React清单)**

## React Redux

152. ### 讲讲flux是啥?

     *Flux* is an *application design paradigm* used as a replacement for the more traditional MVC pattern. It is not a framework or a library but a new kind of architecture that complements React and the concept of Unidirectional Data Flow. Facebook uses this pattern internally when working with React.

     The workflow between dispatcher, stores and views components with distinct inputs and outputs as follows:

     ![](flux.png)

     **[⬆ 回顶部](#React清单)**

153. ### 介绍下Redux是啥?

     *Redux* is a predictable state container for JavaScript apps based on the *Flux design pattern*. Redux can be used together with React, or with any other view library. It is tiny (about 2kB) and has no dependencies.

     **[⬆ 回顶部](#React清单)**

154. ### Redux的核心理念是啥?

     Redux follows three fundamental principles:

     1. **Single source of truth:** The state of your whole application is stored in an object tree within a single store. The single state tree makes it easier to keep track of changes over time and debug or inspect the application.
     2. **State is read-only:** The only way to change the state is to emit an action, an object describing what happened. This ensures that neither the views nor the network callbacks will ever write directly to the state.
     3. **Changes are made with pure functions:** To specify how the state tree is transformed by actions, you write reducers. Reducers are just pure functions that take the previous state and an action as parameters, and return the next state.

     **[⬆ 回顶部](#React清单)**

155. ### Redux相比flux有哪些缺点?

     Instead of saying downsides we can say that there are few compromises of using Redux over Flux. Those are as follows:

     1. **You will need to learn to avoid mutations:** Flux is un-opinionated about mutating data, but Redux doesn't like mutations and many packages complementary to Redux assume you never mutate the state. You can enforce this with dev-only packages like `redux-immutable-state-invariant`, Immutable.js, or instructing your team to write non-mutating code.
     2. **You're going to have to carefully pick your packages:** While Flux explicitly doesn't try to solve problems such as undo/redo, persistence, or forms, Redux has extension points such as middleware and store enhancers, and it has spawned a rich ecosystem.
     3. **There is no nice Flow integration yet:** Flux currently lets you do very impressive static type checks which Redux doesn't support yet.

     **[⬆ 回顶部](#React清单)**

156. ### mapStateToProps和mapDispatchToProps有啥不同?

     `mapStateToProps()` is a utility which helps your component get updated state (which is updated by some other components):

     ```javascript
     const mapStateToProps = (state) => {
       return {
         todos: getVisibleTodos(state.todos, state.visibilityFilter)
       }
     }
     ```

     `mapDispatchToProps()` is a utility which will help your component to fire an action event (dispatching action which may cause change of application state):

     ```javascript
     const mapDispatchToProps = (dispatch) => {
       return {
         onTodoClick: (id) => {
           dispatch(toggleTodo(id))
         }
       }
     }
     ```

     **[⬆ 回顶部](#React清单)**

157. ### 可以在reducer中dispatch一个action吗?

     Dispatching an action within a reducer is an **anti-pattern**. Your reducer should be *without side effects*, simply digesting the action payload and returning a new state object. Adding listeners and dispatching actions within the reducer can lead to chained actions and other side effects.

     **[⬆ 回顶部](#React清单)**

158. ### 在组件外如何获取store?

     Yes. You just need to export the store from the module where it created with `createStore()`. Also, it shouldn't pollute the global window object.

     ```javascript
     store = createStore(myReducer)

     export default store
     ```

     **[⬆ 回顶部](#React清单)**

159. ### MVW模式有哪些缺点?

     1. The DOM manipulation is very expensive which causes applications behaves slowly and inefficient.
     3. Due to circular dependencies, a complicated model was created around models and views.
     3. Lot of data changes happens for collaborative applications(like Google Docs).
     4. No way to do undo (travel back in time) easily without adding so much extra code.

     **[⬆ 回顶部](#React清单)**

160. ### Redux和RxJS有哪些相似之处?

     These libraries are very different for very different purposes, but there are some vague similarities.

     Redux is a tool for managing state throughout the application. It is usually used as an architecture for UIs. Think of it as an alternative to (half of) Angular. RxJS is a reactive programming library. It is usually used as a tool to accomplish asynchronous tasks in JavaScript. Think of it as an alternative to Promises. Redux uses the Reactive paradigm because the Store is reactive. The Store observes actions from a distance, and changes itself. RxJS also uses the Reactive paradigm, but instead of being an architecture, it gives you basic building blocks, Observables, to accomplish this pattern.

     **[⬆ 回顶部](#React清单)**

161. ### 页面的加载中咋dispatch一个action?

     You can dispatch an action in `componentDidMount()` method and in `render()` method you can verify the data.

     ```javascript
     class App extends Component {
       componentDidMount() {
         this.props.fetchData()
       }

       render() {
         return this.props.isLoaded
           ? <div>{'Loaded'}</div>
           : <div>{'Not Loaded'}</div>
       }
     }

     const mapStateToProps = (state) => ({
       isLoaded: state.isLoaded
     })

     const mapDispatchToProps = { fetchData }

     export default connect(mapStateToProps, mapDispatchToProps)(App)
     ```

     **[⬆ 回顶部](#React清单)**

162. ### 咋使用connect?

     You need to follow two steps to use your store in your container:

     1. **Use `mapStateToProps()`:** It maps the state variables from your store to the props that you specify.
     2. **Connect the above props to your container:** The object returned by the `mapStateToProps` function is connected to the container. You can import `connect()` from `react-redux`.

         ```jsx  
         import React from 'react'
         import { connect } from 'react-redux'

         class App extends React.Component {
           render() {
             return <div>{this.props.containerData}</div>
           }
         }

         function mapStateToProps(state) {
           return { containerData: state.data }
         }

         export default connect(mapStateToProps)(App)
         ```

    **[⬆ 回顶部](#React清单)**

163. ### 咋重置redux中的state?

     You need to write a *root reducer* in your application which delegate handling the action to the reducer generated by `combineReducers()`.

     For example, let us take `rootReducer()` to return the initial state after `USER_LOGOUT` action. As we know, reducers are supposed to return the initial state when they are called with `undefined` as the first argument, no matter the action.

     ```javascript
     const appReducer = combineReducers({
       /* your app's top-level reducers */
     })

     const rootReducer = (state, action) => {
       if (action.type === 'USER_LOGOUT') {
         state = undefined
       }

       return appReducer(state, action)
     }
     ```

     In case of using `redux-persist`, you may also need to clean your storage. `redux-persist` keeps a copy of your state in a storage engine. First, you need to import the appropriate storage engine and then, to parse the state before setting it to undefined and clean each storage state key.

     ```javascript
     const appReducer = combineReducers({
       /* your app's top-level reducers */
     })

     const rootReducer = (state, action) => {
       if (action.type === 'USER_LOGOUT') {
         Object.keys(state).forEach(key => {
           storage.removeItem(`persist:${key}`)
         })

         state = undefined
       }

       return appReducer(state, action)
     }
     ```

     **[⬆ 回顶部](#React清单)**

164. ### at在connect装饰器的作用是啥?

     The **@** symbol is in fact a JavaScript expression used to signify decorators. *Decorators* make it possible to annotate and modify classes and properties at design time.

     Let's take an example setting up Redux without and with a decorator.

     * **Without decorator:**

         ```javascript
         import React from 'react'
         import * as actionCreators from './actionCreators'
         import { bindActionCreators } from 'redux'
         import { connect } from 'react-redux'

         function mapStateToProps(state) {
           return { todos: state.todos }
         }

         function mapDispatchToProps(dispatch) {
           return { actions: bindActionCreators(actionCreators, dispatch) }
         }

         class MyApp extends React.Component {
           // ...define your main app here
         }

         export default connect(mapStateToProps, mapDispatchToProps)(MyApp)
         ```

     * **With decorator:**

         ```javascript
         import React from 'react'
         import * as actionCreators from './actionCreators'
         import { bindActionCreators } from 'redux'
         import { connect } from 'react-redux'

         function mapStateToProps(state) {
           return { todos: state.todos }
         }

         function mapDispatchToProps(dispatch) {
           return { actions: bindActionCreators(actionCreators, dispatch) }
         }

         @connect(mapStateToProps, mapDispatchToProps)
         export default class MyApp extends React.Component {
           // ...define your main app here
         }
         ```

     The above examples are almost similar except the usage of decorator. The decorator syntax isn't built into any JavaScript runtimes yet, and is still experimental and subject to change. You can use babel for the decorators support.

     **[⬆ 回顶部](#React清单)**

165. ### React的context和Redux有啥区别?

     You can use **Context** in your application directly and is going to be great for passing down data to deeply nested components which what it was designed for. Whereas **Redux** is much more powerful and provides a large number of features that the Context API doesn't provide. Also, React Redux uses context internally but it doesn't expose this fact in the public API.

     **[⬆ 回顶部](#React清单)**

166. ### 为啥Redux中的state函数叫reducers?

     Reducers always return the accumulation of the state (based on all previous and current actions). Therefore, they act as a reducer of state. Each time a Redux reducer is called, the state and action are passed as parameters. This state is then reduced (or accumulated) based on the action, and then the next state is returned. You could *reduce* a collection of actions and an initial state (of the store) on which to perform these actions to get the resulting final state.

     **[⬆ 回顶部](#React清单)**

167. ### 在Redux中咋用AJAX?

     You can use `redux-thunk` middleware which allows you to define async actions.

     Let's take an example of fetching specific account as an AJAX call using *fetch API*:

     ```javascript
     export function fetchAccount(id) {
       return dispatch => {
         dispatch(setLoadingAccountState()) // Show a loading spinner
         fetch(`/account/${id}`, (response) => {
           dispatch(doneFetchingAccount()) // Hide loading spinner
           if (response.status === 200) {
             dispatch(setAccount(response.json)) // Use a normal function to set the received state
           } else {
             dispatch(someError)
           }
         })
       }
     }

     function setAccount(data) {
      return { type: 'SET_Account', data: data }
     }
     ```

     **[⬆ 回顶部](#React清单)**

168. ### 应该把所有state都放在Redux的store中吗?

      Keep your data in the Redux store, and the UI related state internally in the component.

      **[⬆ 回顶部](#React清单)**

169. ### 访问Redux中store的正确方式是啥?

     The best way to access your store in a component is to use the `connect()` function, that creates a new component that wraps around your existing one. This pattern is called *Higher-Order Components*, and is generally the preferred way of extending a component's functionality in React. This allows you to map state and action creators to your component, and have them passed in automatically as your store updates.

     Let's take an example of `<FilterLink>` component using connect:

     ```javascript
     import { connect } from 'react-redux'
     import { setVisibilityFilter } from '../actions'
     import Link from '../components/Link'

     const mapStateToProps = (state, ownProps) => ({
       active: ownProps.filter === state.visibilityFilter
     })

     const mapDispatchToProps = (dispatch, ownProps) => ({
       onClick: () => dispatch(setVisibilityFilter(ownProps.filter))
     })

     const FilterLink = connect(
       mapStateToProps,
       mapDispatchToProps
     )(Link)

     export default FilterLink
     ```

     Due to it having quite a few performance optimizations and generally being less likely to cause bugs, the Redux developers almost always recommend using `connect()` over accessing the store directly (using context API).

     ```javascript
     class MyComponent {
       someMethod() {
         doSomethingWith(this.context.store)
       }
     }
     ```

     **[⬆ 回顶部](#React清单)**

170. ### 在Redux中component和container有啥区别?

     **Component** is a class or function component that describes the presentational part of your application.

     **Container** is an informal term for a component that is connected to a Redux store. Containers *subscribe* to Redux state updates and *dispatch* actions, and they usually don't render DOM elements; they delegate rendering to presentational child components.

     **[⬆ 回顶部](#React清单)**

171. ### 在Redux中的constants有啥作用?

     Constants allows you to easily find all usages of that specific functionality across the project when you use an IDE. It also prevents you from introducing silly bugs caused by typos – in which case, you will get a `ReferenceError` immediately.

     Normally we will save them in a single file (`constants.js` or `actionTypes.js`).

     ```javascript
     export const ADD_TODO = 'ADD_TODO'
     export const DELETE_TODO = 'DELETE_TODO'
     export const EDIT_TODO = 'EDIT_TODO'
     export const COMPLETE_TODO = 'COMPLETE_TODO'
     export const COMPLETE_ALL = 'COMPLETE_ALL'
     export const CLEAR_COMPLETED = 'CLEAR_COMPLETED'
     ```

     In Redux you use them in two places:

     1. **During action creation:**

         Let's take `actions.js`:

         ```javascript
         import { ADD_TODO } from './actionTypes';

         export function addTodo(text) {
           return { type: ADD_TODO, text }
         }
         ```

     2. **In reducers:**

         Let's create `reducer.js`:

         ```javascript
         import { ADD_TODO } from './actionTypes'

         export default (state = [], action) => {
           switch (action.type) {
             case ADD_TODO:
               return [
                 ...state,
                 {
                   text: action.text,
                   completed: false
                 }
               ];
             default:
               return state
           }
         }
         ```

      **[⬆ 回顶部](#React清单)**

172. ### mapDispatchToProps有哪几种方式绑定action?

     There are a few ways of binding *action creators* to `dispatch()` in `mapDispatchToProps()`. Below are the possible options:

     ```javascript
     const mapDispatchToProps = (dispatch) => ({
      action: () => dispatch(action())
     })
     ```

     ```javascript
     const mapDispatchToProps = (dispatch) => ({
      action: bindActionCreators(action, dispatch)
     })
     ```

     ```javascript
     const mapDispatchToProps = { action }
     ```

     The third option is just a shorthand for the first one.

     **[⬆ 回顶部](#React清单)**

173. ### ownProps在mapStateToProps和mapDispatchToProps中的作用是啥?

     If the `ownProps` parameter is specified, React Redux will pass the props that were passed to the component into your *connect* functions. So, if you use a connected component:

     ```jsx  
     import ConnectedComponent from './containers/ConnectedComponent';

     <ConnectedComponent user={'john'} />
     ```

     The `ownProps` inside your `mapStateToProps()` and `mapDispatchToProps()` functions will be an object:

     ```javascript
     { user: 'john' }
     ```

     You can use this object to decide what to return from those functions.

     **[⬆ 回顶部](#React清单)**

174. ### 咋构建Redux的项目目录?

     Most of the applications has several top-level directories as below:

     1. **Components**: Used for *dumb* components unaware of Redux.
     2. **Containers**: Used for *smart* components connected to Redux.
     3. **Actions**: Used for all action creators, where file names correspond to part of the app.
     4. **Reducers**: Used for all reducers, where files name correspond to state key.
     5. **Store**: Used for store initialization.

     This structure works well for small and medium size apps.

     **[⬆ 回顶部](#React清单)**

175. ### redux-saga是啥?

     `redux-saga` is a library that aims to make side effects (asynchronous things like data fetching and impure things like accessing the browser cache) in React/Redux applications easier and better.

     It is available in NPM:

     ```console
     $ npm install --save redux-saga
     ```

     **[⬆ 回顶部](#React清单)**

176. ### redux-saga的核心模型是啥?

     *Saga* is like a separate thread in your application, that's solely responsible for side effects. `redux-saga` is a redux *middleware*, which means this thread can be started, paused and cancelled from the main application with normal Redux actions, it has access to the full Redux application state and it can dispatch Redux actions as well.

     **[⬆ 回顶部](#React清单)**

177. ### 在redux-saga中call和put有啥区别?

     Both `call()` and `put()` are effect creator functions. `call()` function is used to create effect description, which instructs middleware to call the promise. `put()` function creates an effect, which instructs middleware to dispatch an action to the store.

     Let's take example of how these effects work for fetching particular user data.

     ```javascript
     function* fetchUserSaga(action) {
       // `call` function accepts rest arguments, which will be passed to `api.fetchUser` function.
       // Instructing middleware to call promise, it resolved value will be assigned to `userData` variable
       const userData = yield call(api.fetchUser, action.userId)

       // Instructing middleware to dispatch corresponding action.
       yield put({
         type: 'FETCH_USER_SUCCESS',
         userData
       })
     }
     ```

     **[⬆ 回顶部](#React清单)**

178. ### redux-thunk是啥?

     *Redux Thunk* middleware allows you to write action creators that return a function instead of an action. The thunk can be used to delay the dispatch of an action, or to dispatch only if a certain condition is met. The inner function receives the store methods `dispatch()` and `getState()` as parameters.

     **[⬆ 回顶部](#React清单)**

179. ### redux-saga和redux-thunk有啥区别?

     Both *Redux Thunk* and *Redux Saga* take care of dealing with side effects. In most of the scenarios, Thunk uses *Promises* to deal with them, whereas Saga uses *Generators*. Thunk is simple to use and Promises are familiar to many developers, Sagas/Generators are more powerful but you will need to learn them. But both middleware can coexist, so you can start with Thunks and introduce Sagas when/if you need them.

     **[⬆ 回顶部](#React清单)**

180. ### 了解Redux调试工具吗?

     *Redux DevTools* is a live-editing time travel environment for Redux with hot reloading, action replay, and customizable UI. If you don't want to bother with installing Redux DevTools and integrating it into your project, consider using Redux DevTools Extension for Chrome and Firefox.

     **[⬆ 回顶部](#React清单)**

181. ### Redux调试工具有哪些特性?

     1. Lets you inspect every state and action payload.
     2. Lets you go back in time by *cancelling* actions.
     3. If you change the reducer code, each *staged* action will be re-evaluated.
     4. If the reducers throw, you will see during which action this happened, and what the error was.
     5. With `persistState()` store enhancer, you can persist debug sessions across page reloads.

     **[⬆ 回顶部](#React清单)**

182. ### Redux选择器是啥?

     *Selectors* are functions that take Redux state as an argument and return some data to pass to the component.

     For example, to get user details from the state:

     ```javascript
     const getUserData = state => state.user.data
     ```

     **[⬆ 回顶部](#React清单)**

183. ### Redux表单是啥?

     *Redux Form* works with React and Redux to enable a form in React to use Redux to store all of its state. Redux Form can be used with raw HTML5 inputs, but it also works very well with common UI frameworks like Material UI, React Widgets and React Bootstrap.

     **[⬆ 回顶部](#React清单)**

184. ### Redux表单有哪些主要特性?

       1. Field values persistence via Redux store.
       2. Validation (sync/async) and submission.
       3. Formatting, parsing and normalization of field values.

       **[⬆ 回顶部](#React清单)**

185. ### Redux中咋添加多个中间件?

     You can use `applyMiddleware()`.

     For example, you can add `redux-thunk` and `logger` passing them as arguments to `applyMiddleware()`:

     ```javascript
     import { createStore, applyMiddleware } from 'redux'
     const createStoreWithMiddleware = applyMiddleware(ReduxThunk, logger)(createStore)
     ```

     **[⬆ 回顶部](#React清单)**

186. ### Redux中咋设置初始的state?

     You need to pass initial state as second argument to createStore:

     ```javascript
     const rootReducer = combineReducers({
       todos: todos,
       visibilityFilter: visibilityFilter
     })

     const initialState = {
       todos: [{ id: 123, name: 'example', completed: false }]
     }

     const store = createStore(
       rootReducer,
       initialState
     )
     ```

     **[⬆ 回顶部](#React清单)**

187. ### Redux和Relay有啥不同?

     Relay is similar to Redux in that they both use a single store. The main difference is that relay only manages state originated from the server, and all access to the state is used via *GraphQL* queries (for reading data) and mutations (for changing data). Relay caches the data for you and optimizes data fetching for you, by fetching only changed data and nothing more.

     **[⬆ 回顶部](#React清单)**

## React supported libraries & Integration

192. ### reselect是啥?

     *Reselect* is a **selector library** (for Redux) which uses *memoization* concept. It was originally written to compute derived data from Redux-like applications state, but it can't be tied to any architecture or library.

     Reselect keeps a copy of the last inputs/outputs of the last call, and recomputes the result only if one of the inputs changes. If the the same inputs are provided twice in a row, Reselect returns the cached output. It's memoization and cache are fully customizable.

     **[⬆ 回顶部](#React清单)**

193. ### 了解Flow吗?

     *Flow* is a *static type checker* designed to find type errors in JavaScript. Flow types can express much more fine-grained distinctions than traditional type systems. For example, Flow helps you catch errors involving `null`, unlike most type systems.

     **[⬆ 回顶部](#React清单)**

194. ### Flow和PropTypes之间有啥区别?

     Flow is a *static analysis tool* (static checker) which uses a superset of the language, allowing you to add type annotations to all of your code and catch an entire class of bugs at compile time. PropTypes is a *basic type checker* (runtime checker) which has been patched onto React. It can't check anything other than the types of the props being passed to a given component. If you want more flexible typechecking for your entire project Flow/TypeScript are appropriate choices.

     **[⬆ 回顶部](#React清单)**

195. ### 在React中咋使用Font字体的icons?

     The below steps followed to include Font Awesome in React:

     1. Install `font-awesome`:

     ```console
     $ npm install --save font-awesome
     ```

     2. Import `font-awesome` in your `index.js` file:

     ```javascript
     import 'font-awesome/css/font-awesome.min.css'
     ```

     3. Add Font Awesome classes in `className`:

     ```javascript
     render() {
       return <div><i className={'fa fa-spinner'} /></div>
     }
     ```

     **[⬆ 回顶部](#React清单)**

196. ### 简单介绍下React调试工具?

     *React Developer Tools* let you inspect the component hierarchy, including component props and state. It exists both as a browser extension (for Chrome and Firefox), and as a standalone app (works with other environments including Safari, IE, and React Native).

     The official extensions available for different browsers or environments.
     1. **Chrome extension**
     2. **Firefox extension**
     3. **Standalone app** (Safari, React Native, etc)

     **[⬆ 回顶部](#React清单)**

197. ### 本地文件为啥不会在chrome中加载调试工具?

     If you opened a local HTML file in your browser (`file://...`) then you must first open *Chrome Extensions* and check `Allow access to file URLs`.

     **[⬆ 回顶部](#React清单)**

198. ### React中咋使用Polymer?

     1. Create a Polymer element:

         ```jsx  
         <link rel='import' href='../../bower_components/polymer/polymer.html' />
         Polymer({
           is: 'calender-element',
           ready: function() {
             this.textContent = 'I am a calender'
           }
         })
         ```

     2. Create the Polymer component HTML tag by importing it in a HTML document, e.g. import it in the `index.html` of your React application:

         ```html
         <link rel='import' href='./src/polymer-components/calender-element.html'>
         ```

    3. Use that element in the JSX file:

        ```javascript
        import React from 'react'

        class MyComponent extends React.Component {
          render() {
            return (
              <calender-element />
            )
          }
        }

        export default MyComponent
        ```

    **[⬆ 回顶部](#React清单)**

199. ### React相对于Vue的优势在哪?

     React has the following advantages over Vue.js:

     1. Gives more flexibility in large apps developing.
     2. Easier to test.
     3. Suitable for mobile apps creating.
     4. More information and solutions available.

     **[⬆ 回顶部](#React清单)**

200. ### React和Angular之间有啥区别?

     | React | Angular |
     | ----- | ------- |
     | React is a library and has only the View layer | Angular is a framework and has complete MVC functionality |
     | React handles rendering on the server side | AngularJS renders only on the client side but Angular 2 and above renders on the server side |
     | React uses JSX that looks like HTML in JS which can be confusing | Angular follows the template approach for HTML, which makes code shorter and easy to understand |
     | React Native, which is a React type to build mobile applications are faster and more stable | Ionic, Angular's mobile native app is relatively less stable and slower |
     | In React, data flows only in one way and hence debugging is easy | In Angular, data flows both way i.e it has two-way data binding between children and parent and hence debugging is often difficult |

     **[⬆ 回顶部](#React清单)**

201. ### 在浏览器调试工具为啥没有React标签?

     When the page loads, *React DevTools* sets a global named `__REACT_DEVTOOLS_GLOBAL_HOOK__`, then React communicates with that hook during initialization. If the website is not using React or if React fails to communicate with DevTools then it won't show up the tab.

     **[⬆ 回顶部](#React清单)**

202. ### 样式型components是啥?

     `styled-components` is a JavaScript library for styling React applications. It removes the mapping between styles and components, and lets you write actual CSS augmented with JavaScript.

     **[⬆ 回顶部](#React清单)**

203. ### 样式型Components长啥样?

     Lets create `<Title>` and `<Wrapper>` components with specific styles for each.

     ```javascript
     import React from 'react'
     import styled from 'styled-components'

     // Create a <Title> component that renders an <h1> which is centered, red and sized at 1.5em
     const Title = styled.h1`
       font-size: 1.5em;
       text-align: center;
       color: palevioletred;
     `

     // Create a <Wrapper> component that renders a <section> with some padding and a papayawhip background
     const Wrapper = styled.section`
       padding: 4em;
       background: papayawhip;
     `
     ```

     These two variables, `Title` and `Wrapper`, are now components that you can render just like any other react component.

     ```jsx  
     <Wrapper>
       <Title>{'Lets start first styled component!'}</Title>
     </Wrapper>
     ```

     **[⬆ 回顶部](#React清单)**

204. ### Relay是啥?

     Relay is a JavaScript framework for providing a data layer and client-server communication to web applications using the React view layer.

     **[⬆ 回顶部](#React清单)**

205. ### 在create-react-app中咋使用Typescript?

     When you create a new project supply `--scripts-version` option as `react-scripts-ts`. `react-scripts-ts` is a set of adjustments to take the standard `create-react-app` project pipeline and bring TypeScript into the mix.

     Now the project layout should look like the following:

     ```
     my-app/
     ├─ .gitignore
     ├─ images.d.ts
     ├─ node_modules/
     ├─ public/
     ├─ src/
     │  └─ ...
     ├─ package.json
     ├─ tsconfig.json
     ├─ tsconfig.prod.json
     ├─ tsconfig.test.json
     └─ tslint.json
     ```

     **[⬆ 回顶部](#React清单)**

## Miscellaneous

206. ### reselect有哪些主要特性?

       1. Selectors can compute derived data, allowing Redux to store the minimal possible state.
       2. Selectors are efficient. A selector is not recomputed unless one of its arguments changes.
       3. Selectors are composable. They can be used as input to other selectors.

       **[⬆ 回顶部](#React清单)**

207. #### reselect的用法是啥?

     Let's take calculations and different amounts of a shipment order with the simplified usage of Reselect:

     ```javascript
     import { createSelector } from 'reselect'

     const shopItemsSelector = state => state.shop.items
     const taxPercentSelector = state => state.shop.taxPercent

     const subtotalSelector = createSelector(
       shopItemsSelector,
       items => items.reduce((acc, item) => acc + item.value, 0)
     )

     const taxSelector = createSelector(
       subtotalSelector,
       taxPercentSelector,
       (subtotal, taxPercent) => subtotal * (taxPercent / 100)
     )

     export const totalSelector = createSelector(
       subtotalSelector,
       taxSelector,
       (subtotal, tax) => ({ total: subtotal + tax })
     )

     let exampleState = {
       shop: {
         taxPercent: 8,
         items: [
           { name: 'apple', value: 1.20 },
           { name: 'orange', value: 0.95 },
         ]
       }
     }

     console.log(subtotalSelector(exampleState)) // 2.15
     console.log(taxSelector(exampleState))      // 0.172
     console.log(totalSelector(exampleState))    // { total: 2.322 }
     ```

     **[⬆ 回顶部](#React清单)**

208. ### Redux中的action长啥样的?

     *Actions* are plain JavaScript objects or payloads of information that send data from your application to your store. They are the only source of information for the store. Actions must have a type property that indicates the type of action being performed.

     For example an example action which represents adding a new todo item:

     ```javascript
     {
       type: ADD_TODO,
       text: 'Add todo item'
     }
     ```

     **[⬆ 回顶部](#React清单)**

209. ### ES6写的Class组件中能使用静态对象吗?

     No, `statics` only works with `React.createClass()`:

     ```javascript
     someComponent= React.createClass({
       statics: {
         someMethod: function() {
           // ..
         }
       }
     })
     ```

     But you can write statics inside ES6+ classes like this:

     ```javascript
     class Component extends React.Component {
       static propTypes = {
         // ...
       }

       static someMethod() {
         // ...
       }
     }
     ```

     **[⬆ 回顶部](#React清单)**

210. ### Redux只能在React中使用吗?

     Redux can be used as a data store for any UI layer. The most common usage is with React and React Native, but there are bindings available for Angular, Angular 2, Vue, Mithril, and more. Redux simply provides a subscription mechanism which can be used by any other code.

     **[⬆ 回顶部](#React清单)**

211. ### 使用Redux需要特殊的工具构建吗?

     Redux is originally written in ES6 and transpiled for production into ES5 with Webpack and Babel. You should be able to use it regardless of your JavaScript build process. Redux also offers a UMD build that can be used directly without any build process at all.

     **[⬆ 回顶部](#React清单)**

212. ### Redux表单咋从state中获取初始值?

     You need to add `enableReinitialize : true` setting.

     ```javascript
     const InitializeFromStateForm = reduxForm({
       form: 'initializeFromState',
       enableReinitialize : true
     })(UserEdit)
     ```

     If your `initialValues` prop gets updated, your form will update too.

     **[⬆ 回顶部](#React清单)**

213. ### PropTypes中咋给prop变量设置多个类型?

     You can use `oneOfType()` method of `PropTypes`.

     For example, the height property can be defined with either `string` or `number` type as below:

     ```javascript
     Component.PropTypes = {
       size: PropTypes.oneOfType([
         PropTypes.string,
         PropTypes.number
       ])
     }
     ```

     **[⬆ 回顶部](#React清单)**

214. ### React中能引入SVG文件作为组件吗?

     You can import SVG directly as component instead of loading it as a file. This feature is available with `react-scripts@2.0.0` and higher.

     ```jsx  
     import { ReactComponent as Logo } from './logo.svg'

     const App = () => (
       <div>
         {/* Logo is an actual react component */}
         <Logo />
       </div>
     )
     ```

     **Note**: Don't forget about the curly braces in the import.

     **[⬆ 回顶部](#React清单)**

215. ### 为啥不推荐写行列式或者函数式的ref?

     If the ref callback is defined as an inline function, it will get called twice during updates, first with null and then again with the DOM element. This is because a new instance of the function is created with each render, so React needs to clear the old ref and set up the new one.

     ```jsx
     class UserForm extends Component {
       handleSubmit = () => {
         console.log("Input Value is: ", this.input.value)
       }


       render () {
        return (
          <form onSubmit={this.handleSubmit}>
            <input
              type='text'
              ref={(input) => this.input = input} /> // Access DOM input in handle submit
            <button type='submit'>Submit</button>
          </form>
        )
      }
     }
     ```

     But our expectation is for the ref callback to get called once, when the component mounts. One quick fix is to use the ES7 class property syntax to define the function

     ```jsx
     class UserForm extends Component {
      handleSubmit = () => {
        console.log("Input Value is: ", this.input.value)
      }

      setSearchInput = (input) => {
        this.input = input
      }

      render () {
        return (
          <form onSubmit={this.handleSubmit}>
            <input
              type='text'
              ref={this.setSearchInput} /> // Access DOM input in handle submit
            <button type='submit'>Submit</button>
          </form>
        )
      }
     }
     ```

     **[⬆ 回顶部](#React清单)**

216. ### React中的渲染劫持是啥?

     The concept of render hijacking is the ability to control what a component will output from another component. It actually means that you decorate your component by wrapping it into a Higher-Order component. By wrapping you can inject additional props or make other changes, which can cause changing logic of rendering. It does not actually enables hijacking, but by using HOC you make your component behave in different way.

     **[⬆ 回顶部](#React清单)**

217. ### HOC工厂是啥?
     There are two main ways of implementing HOCs in React. 1. Props Proxy (PP) and 2. Inheritance Inversion (II). They follow different approaches for manipulating the *WrappedComponent*.
     **Props Proxy**

     In this approach, the render method of the HOC returns a React Element of the type of the WrappedComponent. We also pass through the props that the HOC receives, hence the name **Props Proxy**.

     ```jsx

     function ppHOC(WrappedComponent) {
      return class PP extends React.Component {
        render() {
          return <WrappedComponent {...this.props}/>
        }
      }
     }
     ```
     **Inheritance Inversion**
     In this approach, the returned HOC class (Enhancer) extends the WrappedComponent. It is called Inheritance Inversion because instead of the WrappedComponent extending some Enhancer class, it is passively extended by the Enhancer. In this way the relationship between them seems **inverse**.

     ```jsx
     function iiHOC(WrappedComponent) {
      return class Enhancer extends WrappedComponent {
        render() {
          return super.render()
        }
      }
     }
     ```

     **[⬆ 回顶部](#React清单)**

218. ### React组件咋传递数字?

     You should be passing the numbers via curly braces({}) where as strings inn quotes

     ```jsx
        React.render(<User age={30} department={"IT"} />, document.getElementById('container'));
     ```

     **[⬆ 回顶部](#React清单)**

219. ### 我应该将所有state都放进Redux中吗，何时用组件内部的state?
     It is up to developer decision. i.e, It is developer job to determine what kinds of state make up your application, and where each piece of state should liveSome users prefer to keep every single piece of data in Redux, to maintain a fully serializable and controlled version of their application at all times. Others prefer to keep non-critical or UI state, such as “is this dropdown currently open”, inside a component's internal state.

     Below are the thumb rules to determine what kind of data should be put into Redux
     1. Do other parts of the application care about this data?
     2. Do you need to be able to create further derived data based on this original data?
     3. Is the same data being used to drive multiple components?
     4. Is there value to you in being able to restore this state to a given point in time (ie, time travel debugging)?
     5. Do you want to cache the data (ie, use what's in state if it's already there instead of re-requesting it)?

     **[⬆ 回顶部](#React清单)**

220. ### React中的registerServerWorker是干啥的?

     React creates a service worker for you without any configuration by default. The service worker is a web API that helps you cache your assets and other files so that when the user is offline or on slow network, he/she can still see results on the screen, as such, it helps you build a better user experience, that's what you should know about service worker's for now. It's all about adding offline capabilities to your site.

     ```jsx
        import React from 'react';
        import ReactDOM from 'react-dom';
        import App from './App';
        import registerServiceWorker from './registerServiceWorker';

        ReactDOM.render(<App />, document.getElementById('root'));
        registerServiceWorker();
     ```

     **[⬆ 回顶部](#React清单)**

221. ### React16中的memo是啥?

     Class components can be restricted from rendering when their input props are the same using **PureComponent or shouldComponentUpdate**. Now you can do the same with function components by wrapping them in **React.memo**.
     ```jsx
     const MyComponent = React.memo(function MyComponent(props) {
      /* only rerenders if props change */
     });
     ```

     **[⬆ 回顶部](#React清单)**

222. ### React16中的lazy是啥?
     The React.lazy function lets you render an dynamic import as a regular component. It will automatically load the bundle containing the OtherComponent when the component gets rendered. This must return a Promise which resolves to a module with a default export containing a React component.
     ```jsx
     const OtherComponent = React.lazy(() => import('./OtherComponent'));

     function MyComponent() {
      return (
        <div>
          <OtherComponent />
        </div>
      );
     }
     ```
     **Note:**
     React.lazy and Suspense is not yet available for server-side rendering. If you want to do code-splitting in a server rendered app, we still recommend React Loadable.

     **[⬆ 回顶部](#React清单)**

223. ### 通过setState咋避免不必要的更新?
     You can compare current value of the state with an existing state value and decide whether to rerender the page or not. If the values are same then you need to return **null** to stop rerendering otherwise return the latest state value. For example, the user profile information is conditionally rendered as follows,
     ```jsx
     getUserProfile = user => {
       const latestAddress = user.address;
       this.setState(state => {
         if (state.address === latestAddress) {
           return null;
         } else {
           return { title: latestAddress };
         }
       });
     };
     ```
224. ### 在React16中咋渲染数组、字符和数字?
     **Arrays**: Unlike older releases, you don't need to make sure **render** method return a single element in React16. You are able to return multiple sibling elements without a wrapping element by returning an array. For example, let us take the below list of developers,
     ```jsx
     const ReactJSDevs = () => {
       return [
         <li key="1">John</li>,
         <li key="2">Jackie</li>,
         <li key="3">Jordan</li>
       ];
     }
     ```
     You can also merge this array of items in another array component
     ```jsx
     const JSDevs = () => {
       return (
         <ul>
           <li>Brad</li>
           <li>Brodge</li>
           <ReactJSDevs/>
           <li>Brandon</li>
         </ul>
       );
     }
     ```
     **Strings and Numbers:** You can also return string and number type from the render method
     ```jsx
     render() {
      return 'Welcome to ReactJS questions';
     }
     // Number
     render() {
      return 2018;
     }
     ```

     **[⬆ 回顶部](#React清单)**
