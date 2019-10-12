---
title: 知乎日报Vue版
date: 2018-08-09 17:49:51
tags:
- Vue
- Vuex
- 动态路由
categories: 前端
---

__知乎日报APP__ 是前端入门各类框架的热门选择，当然还包括某瓣某音乐等。本次项目是基于 __Vue__、__Vue-router__ 及 __Vuex__ 做的知乎日报移动版，对于刚接触 __MVVM__ 类框架或者Vue的新手很适合用来学习，包括组件式复用、API 封装、路由配置及 __动态加载__ 以及组件数据存储的设计等，很值得一试。

<div style="max-width:70%;margin:auto">{% asset_img 0.png %}</div>

<!-- more -->

## 介绍

* 项目基于 [vue-cli](https://github.com/vuejs/vue-cli) 脚手架构建，[webpack](https://webpack.js.org/guides/get-started/) 打包项目。

* 知乎日报的数据来源于 [izzyleung](https://github.com/izzyleung/ZhihuDailyPurify/wiki/知乎日报-API-分析)，在开发环境通过代理形式访问数据源

* 针对前端的数据存储，在多个模块复用的数据采用 [vuex](https://vuex.vuejs.org/) 存储，组件内封闭的状态数据存储在 state

* 前端的路由使用 [vue-router](http://router.vuejs.org/en/)，切换路由时按需加载单页模块资源。

## 构建

[这里](https://github.com/1349279985/zhihudaily-vue2)是项目的 github 地址，欢迎 *Star*

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report

# run unit tests
npm run unit

# run e2e tests
npm run e2e

# run all tests
npm test
```

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