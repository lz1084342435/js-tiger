**对象展开运算符** （也就是**三个点**） 作用跟 Object.assign 很类似，但是用起来更简单傻瓜化。

### 作用

第一，拼接。

```
let aa = { a: 1 }
let bb = { b: 2 }
let cc = { ...aa, ...bb }
/* { a: 1, b: 2 }*/
```

第二，覆盖。

可以对某个对象进行一定的修改。

```js
let aa = { a: 1, b: 2 }
// 现在我想得到一个 { a: 1, b: 3}
let bb = { b: 3 }
let cc = { ...aa, ...bb }
```

上面 cc 就是我们想要的结果。

第三，保护原始值不受修改。上面我们想要得到一个 aa 的修改版，但是其实用对象展开运算符，通常是不修改原始数据的，也就是 aa 并没有被改变。

这个特性让 [redux 对它非常青睐](http://redux.js.org/docs/recipes/UsingObjectSpreadOperator.html)


### 兼容性

目前，[对象展开运算符还没有进入 ES 标准](https://github.com/tc39/proposal-object-rest-spread) 。所以各大浏览器和 Nodejs 都不支持它。好在，未来我们使用的 create-react-app 环境是支持它的。
