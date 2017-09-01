解构赋值，是后续我们开发中非常常用的一种赋值方式。它的特点是简短和易懂，并没有提供什么以前不能完成的功能，所以可以认为是一种语法糖。

比如我有一个对象：

```
const user = { name: ‘happypeter’, email: 'peter@peter.com', wechat: 'happypeter1983' }

let name = user.name
let email = user.email
let wechat = user.wechat
```

这样，我们就可以把 obj 中的数据，单独赋值给某个变量来使用了。完全不用依赖于解构赋值。但是，如果用解构，那么语句会简单很多

```
const { name, email, wechat } = user
```

### 数组

数组上也能用。

```
let [a, b, c] = [1, 2, 3]
```

### 参考

http://es6.ruanyifeng.com/#docs/destructuring
