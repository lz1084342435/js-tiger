本节把整个应用做的完善一些：

- 添加 React-Router 进来，让首页显示多篇文章
- 每篇文章拥有自己的点赞和评论

### 添加 React-Router

区分出两个页面来。

- [add HomePage](https://github.com/happypeter/redux-hello/commits)
- [add two posts](https://github.com/happypeter/redux-hello/commits)

### 添加另一组评论，每篇 post 显示自己的评论

- [post show its own comments](https://github.com/happypeter/redux-hello/commits)


- [ADD_COMMENT works again](https://github.com/happypeter/redux-hello/commits)


### 点赞功能

重新规划一下数据，把点赞功能也实现了


- [post show its own post](https://github.com/happypeter/redux-hello/commits)


- [INCREMENT_LIKES works again](https://github.com/happypeter/redux-hello/commits)

关于如何更新一个由对象组成的数组，参考：http://redux.js.org/docs/recipes/reducers/RefactoringReducersExample.html

### 细节调整

添加 Header

- [add Header](https://github.com/happypeter/redux-hello/commits)


### 总结

目前 redux 的知识，基本讲完。还有一个负责 ajax 请求的 redux-thunk ，作为选学内容。
