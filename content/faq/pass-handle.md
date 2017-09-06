一个非常常见的操作，就是执行事件处理函数的时候，需要传递一定的参数。


### 基本案例

```js
import React, { Component } from 'react'
import './app.css'

class App extends Component {
  handleClick = (name) => {
    console.log(`hello ${name}`)
  }


  render () {
    let name = 'happypeter'
    return (
      <div className='app'>
        <div onClick={() => this.handleClick(name)}
          className='button'>
          click me
        </div>
      </div>
    )
  }
}

export default App
```

### 代码

pass-param
