### 基本用法

先写一个路由传参数的 Hello World 。


代码

```js
import React, { Component } from 'react'
import './app.css'
import {
  BrowserRouter as Router,
  Route,
  Link
} from 'react-router-dom'


class Post extends Component {
  render () {
    const { title } = this.props.match.params
    return (
      <div className='Post'>
        <h1>
          {title}
        </h1>
      </div>
    )
  }
}


class App extends Component {

  render () {
    return (
      <Router>
        <div>
          <Link to='/post/git'>Git 文章</Link>
          <Link to='/post/cli'>Cli 文章</Link>
          <Route path='/post/:title' component={Post} />
        </div>
      </Router>
    )
  }
}

export default App
```

视频：http://digicity-1253322599.costj.myqcloud.com/router-params-hello.mp4

### 打怪

我们要展示一系列的内容，例如博客就会用到如下的 url

```
example.com/post/1
example.com/post/2
...
```




那么对应的路由如何写呢？这个就涉及到了路由传参的技巧。


### 实现首页上的文章列表

```js
import React, { Component } from 'react'
import './app.css'
import {
  BrowserRouter as Router,
  Route,
  Link
 } from 'react-router-dom'


class App extends Component {

  state = {
    posts: [
      {
        id: '134',
        title: 'Git 使用技巧',
        content: 'main content'
      },
      {
        id: '256',
        title: '命令使用技巧',
        content: 'main content'
      },
      {
        id: '545',
        title: 'Github 基础',
        content: 'main content'
      }
    ]
  }

  render () {

    const postList = this.state.posts.map((t, i) => (
      <li key={i}>
        <Link to={`/post/${t.id}`}>
          {t.title}
        </Link>
      </li>
    ))
    return (
      <Router>
        <div>
          <ul>
            {postList}
          </ul>
        </div>
      </Router>
    )
  }
}

export default App
```

视频： http://digicity-1253322599.costj.myqcloud.com/post-list.mp4

### 接受参数

参数必然是有人传递（ Link 中传递），有人中转（ Route ），有人接收（ Route 对应的组件，例如 Post.js）。

视频：http://digicity-1253322599.costj.myqcloud.com/pass-params.mp4


### 显示文章详情

Post.js 中


```js
import React, { Component } from 'react'

class Post extends Component {

  state = {
    posts: [
      {
        id: '134',
        title: 'Git 使用技巧',
        content: 'main content'
      },
      {
        id: '256',
        title: '命令使用技巧',
        content: 'main content'
      },
      {
        id: '545',
        title: 'Github 基础',
        content: 'main content'
      }
    ]
  }


  render () {
    const { id } = this.props.match.params
    const { posts } = this.state
    const post = posts.find(t => t.id === id)
    console.log('post.....', post)
    return (
      <div className='Post'>
        <h1>
          {post.title}
        </h1>
        <p>
          {post.content}
        </p>
      </div>
    )
  }
}

export default Post
```

视频：http://digicity-1253322599.costj.myqcloud.com/show-post.mp4


接下来我们继续上面的案例写，来把这个博客系统做的功能完整些。

### router 配合 Layout 文件使用

App.js 中，这样写

```
<Router>
  <Layout>
    <Main />
  </Layout>
</Router>
```

Main.js 中

```js
<div className='main'>
  <Route exact path='/' component={Home} />
  <Route path='/post/:id' component={Post} />
</div>
```

视频：http://digicity-1253322599.costj.myqcloud.com/router-layout.mp4


### 最终代码

https://github.com/happypeter/dj-demos/tree/master/react-router-demo
