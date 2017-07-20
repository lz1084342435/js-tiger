这一节来看看 redux 如何处理多类数据。

### 添加点赞功能

目前 PostBody 组件中只显示评论，现在我们在添加一个点赞的按钮进来。

- [add likes button](https://github.com/happypeter/redux-hello/commits)


### Store 中存入多类数据

在去创建一个 likeReducer ，然后 reducers/index.js 中这样写

```
import likeReducer from './like'
import commentReducer from './comment'
import { combineReducers } from 'redux'


const rootReducer = combineReducers({
  comments: commentReducer,
  likes: likeReducer
})


export default rootReducer
```

注意，上面的 `comments` 和 `likes` 最终对应了 store.getState() 输出的状态数的对象的两个 key 。

- [state tree with more data](https://github.com/happypeter/redux-hello/commits)


### 显示“0赞”

到 PostBody.js 中，有

```
const mapStateToProps = (state) => ({
  comments: state
})
```

其中的 `state` 代表整个状态树，也就是跟 store.getState() 结果一致。所以要改变为


```
const mapStateToProps = (state) => ({
  comments: state.comments
})
```

对应 likes

```
const mapStateToProps = (state) => ({
  comments: state.comments,
  likes: state.likes
})
```

- [show 0 likes](https://github.com/happypeter/redux-hello/commits)


### 修复评论功能

- [add comments still works](https://github.com/happypeter/redux-hello/commits)

ADD_COMMENTS 对应的 reducer 其实什么都不用动，依然工作良好。

### 添加点赞功能

- [INCREMENT_LIKE](https://github.com/happypeter/redux-hello/commits)
