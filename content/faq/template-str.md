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

如上，模板字符串中，嵌入 JS 变量（或者语句）的方式就是

```
${}
```

用上面的形式包裹。


### 给出定义

综上，给出**模板字符串**的一句话定义：

>到引号包裹的，其中可以嵌入 JS 语句的字符串

参考：

- http://es6.ruanyifeng.com/#docs/string#模板字符串
