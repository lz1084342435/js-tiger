胖箭头函数（ arrow function ) 是非常常用的。从此我们的函数可以写的更为简短，同时省去了绑定 this 的麻烦。

原本函数我们要写成

```js
const myFun = function (name) {
  console.log(name)
}
```

现在可以写成

```js
const myFun = (name) => {
  console.log(name)
}

myFun('happypeter')
```

同时，如果参数只有一个，那么可以把括号去掉，写成

```
const myFun = name => {
  console.log(name)
}

myFun('happypeter')
```

同时，如果里面的语句只有一条，那么花括号也可省去。

```js
const myFun = name =>
  console.log(name)

myFun('happypeter')
```

既然，语句很少，那么写到一行上也可以。

```js
const myFun = name => console.log(name)

myFun('happypeter')
```

如果，我希望函数最终返回 name 的两倍。那我可以写成

```js
const myFun = name => {
  return name + name
}

console.log(myFun('happypeter'))
```

但是，箭头函数还有一个好处，默认就 return 最后的那个东西。所以可以写成

```js
const myFun = name => name + name
```

### 为何要把函数弄得这么简短

因为 JS 特别强调**函数式编程**，也就是经常弄一些无名函数，作为另外一个高阶函数的参数，传来传去，那么这样定义函数时语句的简短就显得非常有必要了。

### 另外一个好处：this 穿透

老的函数写法，需要经常 bind(this) ，因为 this 是不穿透的，箭头函数默认可以让父作用域的 this 直接*穿透*进来，所以一般不需要 bind(this) 。

### 参考

- http://es6.ruanyifeng.com/#docs/function#箭头函数
- http://haoduoshipin.com/v/211.html
