---
title: 如何在Vue中优雅的使用图片懒加载
date: 2021-10-27 22:14:29
tags: [vue, JavaScript]
categories:
- 前端
---


####安装vue-lazyload

```shell
npm i vue-lazyload -S


```
### 在main.js配置文件引入
```javascript
import VueLazyload from 'vue-lazyload'
Vue.use(VueLazyload, {
    preLoad: 1.3, //预加载高度
    error: require('../static/img/error.jpg'), //错误展示图片
    loading: require('../static/img/loading.gif'), //加载等待图片
    attempt: 1 //尝试次数
})

```

### 使用, 将img标签的src换成v-lazy即可
```html
<img v-lazy="http://www.baidu.com/userImg.png" alt="" />
```
### 如果在不同的页面中显示不同的加载占位图，写法如下
```html
<img v-lazy="{src: item.imgUrl, loading: 'http://xx.com/loading.png'}" alt="" />
```
### 背景图也可以使用懒加载

```html
v-lazy:background-image="{src: item.imgUrl, error: 'http://xx.com/error.png', loading: 'http://xx.com/loading.png'}"
```
### 注意

mint-ui已经引入了vue-lazyload，但是在main.js中配置无效。如果需要配置的时候，请重新下载；不需要配置，直接使用v-lazy即可
