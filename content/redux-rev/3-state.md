这一集不涉及 Redux ，我们只是使用每个组件自己的 State 来达成基本评论框效果。

要求：不需要使用后台。直接把假数据设置到 state 变量里面。

### 任务一： 显示两条死的评论在页面上。

这里的体现出 React 的特点，就是所有的组件显示出来的动态数据，都要存放到 state 值之中。

但是数据到底要存储成何种数据类型呢？也即是数据的存储格式要怎么样？

```
this.state = {
  comment1: "hello1",
  comment2: "hello2"，
}
```

这样写，如果只是展示两条死数据，完全没有问题。但是如果有一百条评论，就得有一百个 state 值。但是 React 组件其实一旦写成，它里面的 state 变量名的数量是固定的。代码运行过程中，一般不能添加新的 state 变量进来。只能修改已有的 state 变量值。

数据结构的采用，完全根据实际需要来选择。首先要设置一个 state 变量，就叫 comments 。
同时这个变量里面，可以有多个元素，可以任意增加或者减少元素数量。

```
this.state = {
  comments: [
    "hello1",
    "hello2"
  ]
}
```

代码： [two comments](https://github.com/happypeter/redux-hello/commit/20db7800a8d08cf3c9f0bc40f3dfc35277c795a2)

注意：用数组的 Index 值做 key 是非常不好的习惯，一般用每条数据的 id 来做即可。

### 任务二：添加 form

代码： [form styling](https://github.com/happypeter/redux-hello/commit/af4a6c86e81e00a59088226e67774702206ba225)


### 任务三：发布评论

代码: [submit comment](https://github.com/happypeter/redux-hello/commit/23b7e9aa518f596e961c72362638b019e9d7d441)


注意，不能直接使用下面的代码：

```js
handleSubmit(e) {
  e.preventDefault()
  let content = this.refs.content.value
  let comments =   this.state.comments; // 需要添加 .slice()
  comments.push(content);
  this.setState({ comments });
}
```

因为这样会直接修改 state 值。


参考：

- [为何不能直接修改 State](https://facebook.github.io/react/tutorial/tutorial.html#why-immutability-is-important)

- [中文](https://beijiyang.github.io/react-tutorial-translation/chapter3/content2.html)
