# event-demo

Vue同一元素同时设置click，dblclick事件时:
1. 若click事件不弹出对话框等之类的话，那么双击时，会先执行两次click，然后再执行dblclick事件；<br>
2. 若click事件弹出一个对话框之类的浮层，那么只执行一次click事件且双击事件不会执行, 解决办法就是记录点击次数，延迟执行点击事件。
      

> A Vue.js project
## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report
```

For a detailed explanation on how things work, check out the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).
