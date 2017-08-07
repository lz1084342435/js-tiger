# 基本环境搭建

Vue 比 React 更适合：渐进式。

意思是，公司有个项目，是用 jquery 写的，基本结构就是一个个 html 页面。这时候，可以直接用 script 标签，把 vue 引入到页面中，直接进行页面功能增强。

>Vue 离开了 webpack 可以做很多事情，但是 React 离开 webpack 的确就非常不方便了


所以说，最简单的基本环境就是，html 中直接跟 jQuery 一样，引入使用即可。

但是，我们作为学过 React 的人，从另外一个更专业化的角度入门更好。


### 使用官方的 vue-cli


vue-cli 其中 cli ，cli 的意思是命令行。vue-cli 的作用就是搭建开发基础环境的。相当于 react 的，create-react-app 。


参考： https://github.com/vuejs/vue-cli

> Simple CLI for scaffolding Vue.js projects

> 简单的命令行，用来生成 Vuejs 项目脚手架


Vue-cli 对比于 create-react-app ，有一个优势，就是可以生成多种脚手架（通过替换模板 template 来实现）。


```
vue init <template-name> <project-name>
```

我们选择最专业的模板，也就是 `webpack` 模板。

运行

```
vue init webpack vuex-demo
```


选项中，比较重要的就是选择使用

- Standard ： JS ”标准“ 代码风格
  - https://standardjs.com/
- Airbnb : Airbnb 公司的代码风格
  - https://github.com/airbnb/javascript

对于 Peter 来说，二者最大的区别就是，写不写分号，Peter 不喜欢写分号，所以选择 Standard 。

### 路由 vue-router


把历史从 hash 历史，改为 `/历史` （标准说法应该叫 history 历史，因为使用 history 这个包来达成的）。

如何启动 `history 历史` 呢？

```
mode: history
```

参考：https://router.vuejs.org/zh-cn/essentials/history-mode.html


### 充电：Standard 标准的执行

代码报错：

```
Missing space before value for key 'name'  
  src/router/index.js:13:12
        name:'Home',
```

意思是：在 name 键的值之前，少一个空格。这个不是 js 语法错误，这个是 Standard 代码风格的要求。


### router-link

- https://router.vuejs.org/zh-cn/api/router-link.html


### 添加新的组件

到 Post.vue 里面，添加两个子组件 PostBody.vue CommentBox.vue 。

这里采用：https://cn.vuejs.org/v2/guide/components.html#局部注册


### CSS 相关知识

如果组件内的 CSS ，不希望影响其他组件，那就加上 `scoped` 属性。

scope 的意思是“作用域”，scoped 意思是”被限制作用域的“
