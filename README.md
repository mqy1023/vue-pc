# vue简单pc端项目

> 去年跟着慕课网上vue入门教程的学习代码

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build
```

##### 一、vue-resource通过XMLHttpRequrest或JSONP技术实现异步加载服务端数据的Vue插件
```
this.$http({
    url: '',
    method: 'POST',
    // 请求体重发送的数据
    data: {
        userId: 1
    },
    // 设置请求头
    headers: {
        'Content-Type': 'x-www-from-urlencoded'
    }
}).then(function () {
    // 请求成功回调
}, function () {
    // 请求失败回调
});
```

##### 二、使用express和body-parse(解析json)来返回本地数据
参考`build/dev-server.js` 文件
