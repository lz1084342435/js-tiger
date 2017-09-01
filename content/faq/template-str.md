以前拼接字符串，我们用 `+` ，语句长，而且总是忘写空格。

```
const name = 'happypeter'
let str = 'My Name is ' + name
```

现在有了模板字符串，就非常舒服了。

```
const name = 'happypeter'
let str = `My Name
  is ${name}`
```

上面的引号不是单引号，而是**倒引号** 。倒引号里面不仅仅可以写变量，还可以直接加换行。

参考：

- http://es6.ruanyifeng.com/#docs/string#模板字符串
