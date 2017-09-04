# this 的常见使用

如果有这样的一个 class

```
class Person {
  name = 'peter'

  sayHello () {
    console.log('hello')
  }
}
```

那么，如果我想在 Person 内部的其他函数中使用 sayHello 或者 name 。

那么下面这种使用方式是不行的


```
class Person {
  name = 'peter'

  sayHello () {
    console.log('hello')
  }

  render () {
    sayHello()
    console.log(name)
  }
}
```

会报错，说 sayHello 和 name 都没有定义。

添加 this 关键字，可以解决这个问题


```
class Person {
  name = 'peter'

  sayHello () {
    console.log('hello')
  }

  render () {
    this.sayHello()
    console.log(this.name)
  }
}
```
