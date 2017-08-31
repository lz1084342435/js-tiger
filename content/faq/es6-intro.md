ES 是 JavaScript 的背后的标准名。ES6 是 JS 的新标准，目前人们提到 ES6 指的就是“新 JS” 。

ES6 的功能，浏览器只能大部分支持，所以如果我们在开发的时候，用到 ES6 ，那么一定涉及到一个*编译*的概念。更准确的说法叫”预处理“或者””转译“（因为整个过程就是把 ES6 转换为老 JS 语法，保证浏览器可以支持）。


### ES6 就是一套新 JS 语法的总和

具体涉及到哪些功能，可以参考：

- http://es6.ruanyifeng.com/


### 如何”转译“ ES6 ？

使用 Babel 来进行转译。可以到 https://babeljs.io/ 去试用一下 babel 。但是，实际开发中，我们都是在命令行中去自动化的使用 Babel 。

Babel 的官网在：http://babeljs.io/ 。官网上对它的描述是：

> 一个 Javascript 的编译器( compiler )

我们知道的 create-react-app 这个开发环境，其中就集成了 Babel 。

### 为何要使用 ES6 ？

第一，好用。

第二，大家都用。你不用你就 OUT 。
