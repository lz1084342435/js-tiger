### 问：什么是 nodejs ？

nodejs 是 many things 。

nodejs 是一个 JS 的运行环境。nodejs 出现之前，我们要运行 js 就离不了浏览器。但是自从，2009年 nodejs 被发明之后，我们在自己的服务器上也可以运行 JS 了。

例如，我们要执行一条 JS 语句。

```
console.log('hello')
```

以前我们只能去浏览器里执行。但是现在，我们可以这样，写一个 index.js

```
console.log('hello')
```

然后命令行中运行

```
node index.js
```

就可以执行成功了，整个过程是没有浏览器参与的。

### Nodejs 的意义

一个 web 项目，都有前端代码和后端组成，前台代码都是用 html+css+js 来写的，但是传统上由于本地机器不能运行 JS ，所以后台代码是不能用 JS 来写的，于是我们还要学另外一种语言才能写 Web 程序，通常用来写 Web 后台程序的语言有：PHP , Java ，C# ，Python ，Ruby ，Go ...

所以 Nodejs 的意义就在于，现在开发者终于只用学一种语言，就可以同时进行前端和后端的开发了。
