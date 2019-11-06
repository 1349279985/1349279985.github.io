---
title: 实战写一个实际项目中的PostCss插件
date: 2019-11-06 14:39:07
tags: 
- Webpack
categories: 前端
keywords: 
- Webpack
- 插件
- postcss
- loader
- plugin
---

__PostCss__ 是个好工具，基于它转换的 __AST__ 可以做很多有趣的东西，这篇文章从一个实际的需求出发，教大家写一个可应用于 __webapck__ 打包过程中 __PostCss__ 插件，提供一种自动化处理 __css__ 样式的思路。

<div style="max-width:70%;margin:auto">{% asset_img 0.png %}</div>

<!-- more -->

## 需求背景

在后台前端应用的开发中，经常会用到各类 __UI__ 组件库，假如项目中用到了知名的 [__antd__](https://ant.design/docs/react/customize-theme-cn)，但是需要对应用的各个基础组件做一次换肤，而 __antd__ 只有定制化的几种色号可选，这次要做的是将基础组件的色号都换成美团黄，所以 __antd__ 没法满足需求。当然我们可以在样式表中手动改写 __antd__ 的样式以达到目标，但是这并不方便。我们沿着自动化的思路想，可以在打包过程中对所有样式做统一处理并做一层转换，而样式的解析转换刚好是 __loader__ 的工作，在此实现这一思路会非常合适。

![](1.png)

## 开发思路

在项目中经常会用到 __PostCss__ 做一些插件化的事情包括 __AutoPrefixer__ 等，__PostCss__ 会将 __css__ 样式转为 __AST__ 树方便处理，基于此可以对 __AST__ 上的节点信息做一些处理以贴合本次的需求。如下是一个 __PostCss__ 转换 __css__ 的一个示例。

![](2.png)

转换后的结构就像包含了很多层级树一样，第一层是 __root__ 节点，每个 __css__ 文件就相当于一个 __root__ 节点，每个 __root__ 节点包含的是子节点集合即 __type__ 为 __rule__ 的节点，对应于 __css__ 中的样式块，每个样式块即 __type__ 为 __decl__ 包含书写的 __css__ 键值对集合，__prop__ 对应于健，而 __value__ 就是值了。可以想到，只要遍历获取这些值再转换目标值为需要的值即可。

## 程序设计

既然是做成插件化，则需考虑通用性，可从需求中提取通用性信息包括目标色值即美团黄和文件路径，可作为插件的入参。

__PostCss__ 提供了很多 [__API__](https://api.postcss.org/postcss.html) 方便操作转换后 __AST__ 树，此次分析后只用到如下遍历相关 __API__ 即可

- [__walk__](https://api.postcss.org/AtRule.html#walk): 遍历所有节点信息
- [__walkAtRules__](https://api.postcss.org/AtRule.html#walkAtRules): 遍历所有 __atrule__ 类型节点
- [__walkRules__](https://api.postcss.org/AtRule.html#walkRules): 遍历所有 __rule__ 类型节点
- [__walkComments__](https://api.postcss.org/AtRule.html#walkComments): 遍历所有 __comment__ 类型节点
- [__walkDecls__](https://api.postcss.org/AtRule.html#walkDecls): 遍历所有 __decl__ 类型节点

__PostCss__ 的作用只适用 __css__ 样式文件，如果是预编译类型样式如 __less__，则需要先转换为 __css__ 后再做处理，在配置 __loader__ 时注意下先后顺序即可。插件的核心逻辑是获取到 __decl__ 节点中的 __value__ 并进行替换。

```js
const postcss = require('postcss');

const postcssPluginParseMargin = postcss.plugin('transform-color', opts => {
  opts = opts || {};
  const { colorMap } = opts;
  return root => {
    root.walkRules(rule => {
      rule.walkDecls(function (decl, i) {
        colorMap.forEach(({ source, target }) => {
          if (decl.value.indexOf(source) !== -1) {
            decl.value = decl.value.replace(source, target);
          }
        });
      });
    });
  };
});

const cssStyle = `
	.test {
    font-size: 13px;
    color: #1890ff;
  }
	.test a {
    font-size: 14px;
    background-color: #1890ff;
    color: #1890ff
  }
	.test b {
    font-size: 15px;
	}
`;

const config = {
  colorMap: [
    { source: '#1890ff', target: '#ffbd00' }
  ]
}

postcss([postcssPluginParseMargin(config)]).process(cssStyle).then(function(res){
	console.log(res.cssStyle);
});

/** 
.test {
  font-size: 13px;
  color: #ffbd00;
}
.test a {
  font-size: 14px;
  background-color: #ffbd00;
  color: #ffbd00
}
.test b {
  font-size: 15px;
}
*/

```

以上通过模拟 __cssStyle__ 模拟了 __root__，将 __css__ 文件 __cssStyle__ 作为源文件输入，首先通过 __PostCss__ 转译为如下 __AST__ 并深度遍历，先遍历 __rule__ 节点再遍历 __decl__ 节点，最后匹配 __value__ 是否符合 __config__ 中的 __source__，是则替换为美团黄。

![](3.png)

## 引入插件

而如果在 __webpack__ 中使用自定义的插件，则需要在 __loaders__ 进行对应的配置，如下在 __webapck__ 的 __loaders__ 中，在 __postcss__ 的 __loader__ 中进行自定义插件的配置，并且将文件资源的路径传入检测路径是否匹配目标路径。

```js
  {
    loader: require.resolve('postcss-loader'),
    options: {
      ident: 'postcss',
      plugins: (loader) => [
        require('./postcss-transform-color')({
          colorMap: [
            { source: '#1890ff', target: '#ffbd00' },
          ],
          resourcePath: loader.resourcePath,
        }),
      ],
    },
  }
```
再对自定义插件做一些改写如下，即完成插件的引入，其中 __root__ 代表每一个正在处理的 __css__ 文件转化后的 __AST__。
```js
// postcss-transform-color.js
const postcss = require('postcss');

const alterColorPlugin = postcss.plugin('transform-color', opts => {
  opts = opts || {};
  const { colorMap, resourcePath } = opts;
  return (root, result) => {
    if (/node_modules\/antd/.test(resourcePath)) {
      root.walkRules(rule => {
        rule.walkDecls(function (decl, i) {
          colorMap.forEach(({ source, target }) => {
            if (decl.value.indexOf(source) !== -1) {
              decl.value = decl.value.replace(source, target);
            }
          });
        });
      });
    }
  };
});

module.exports = alterColorPlugin;
```

## 总结

以上针对特定的需求写了一个简单的 __PostCss__ 插件，该插件并不是非常的通用，可能是针对某些项目很适用，但插件大体的写法思路还是有迹可循的。

------