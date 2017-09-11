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
