聊一下**与运算符**的基本原理以及在实际 React 项目中的最常见用法。

### 基本用法

- true&&true 结果：true
- false&&ture 结果：是 false
- false&&false 结果：false

上面的运算是任何科目中统一的规范。

但是 JS 领域，使用 && 的时候，还是有隐含的运行原理的，这个给出了我们很多编程上的方便。

>左侧的数据如果为 true 那么，右侧的语句才会执行，左侧数据如果为 false, 那么右侧语句直接忽略

上面的特性直接就可以应用到实际开发中，来在个别场合，取代三目运算符。

也就是

```
this.state.active ? 'active' : ''
```

可以改写为

```
this.state.active && 'active'
```
