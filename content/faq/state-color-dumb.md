这里给出一个 state 使用的案例，供大家学习。

这里主要涉及的知识点：

- 字符串类 state 的操作
- style 属性的使用

### 比较笨的方法

```js
import React, { Component } from 'react'
import './app.css'

class App extends Component {

  state = {
    background: 'none'
  }

  handleClick = () => {
    this.setState({
      background: 'yellow'
    })
  }

  render () {
    return (
      <div className='app'>
        <div onClick={this.handleClick}
          style={{
            background: this.state.background
          }}
          className='button'>
          click me
        </div>
      </div>
    )
  }
}

export default App
```

视频：state-color-dumb


### 为何笨？

上面的代码，完全符合 react 的 state 标准使用形式。但是如果后续有更丰富的操作，例如单击后改变多条样式规则，上面的方法显得就有些笨了。
