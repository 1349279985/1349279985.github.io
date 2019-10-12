---
title: 知乎日报Vue版
date: 2018-04-03 17:49:51
tags:
- Vue
- Vuex
- 动态路由
- webpack
categories: 前端
---

__知乎日报APP__ 是前端入门各类框架的热门选择，当然还包括某瓣某音乐等。本次项目是基于 __Vue__、__Vue-router__ 及 __Vuex__ 做的知乎日报移动版，对于刚接触 __MVVM__ 类框架或者 __Vue__ 的新手很适合用来学习，包括组件式复用、API 封装、路由配置及 __动态加载__ 以及组件数据存储的设计等，很值得一试。

<div style="max-width:70%;margin:auto">{% asset_img 0.png %}</div>

<!-- more -->

## 介绍

* 项目基于 __[vue-cli3](https://github.com/vuejs/vue-cli)__ 脚手架构建

* 知乎日报的数据来源于 __[izzyleung](https://github.com/izzyleung/ZhihuDailyPurify/wiki/知乎日报-API-分析)__，在开发环境通过代理形式访问数据源

* 针对前端的数据存储，在多个模块复用的数据采用 __[vuex](https://vuex.vuejs.org/)__ 存储，组件内封闭的状态数据存储在 state

* 前端的路由使用 __[vue-router](http://router.vuejs.org/en/)__，切换路由时 __按需加载__ 单页模块资源。

## 构建

__[这里](https://github.com/1349279985/zhihudaily)__ 是项目的 github 地址，欢迎 __Star__

## 安装项目依赖包
```
yarn install or npm install
```

### 本地环境运行并热更新
```
yarn serve or npm run serve
```

### 生产环境打包压缩
```
yarn build or npm run build
```

### eslint 修复文件
```
yarn lint or npm run eslint
```

### 自定义配置
See [Configuration Reference](https://cli.vuejs.org/config/).

## 项目目录

<div style="width:50%;margin:auto">{% asset_img 6.png %}</div>

## 开发环境效果

### 首页

<div style="width:70%;margin:auto">{% asset_img 1.png %}</div>

### 侧栏导航

<div style="width:70%;margin:auto">{% asset_img 2.png %}</div>

### 主题列表页

<div style="width:70%;margin:auto">{% asset_img 3.png %}</div>

### 文章详情页

<div style="width:70%;margin:auto">{% asset_img 4.png %}</div>

### 评论页

<div style="width:70%;margin:auto">{% asset_img 5.png %}</div>

------