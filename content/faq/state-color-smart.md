这集用比较聪明的办法来做一下 **div 变色**问题。

最佳的解决方式是：通过设置 className 中是否 active 来完成。

```
import React, { Component } from 'react'
import './app.css'

class App extends Component {

  state = {
    active: false
  }

  handleClick = () => {
    this.setState({
      active: !this.state.active
    })
  }

  render () {
    return (
      <div className='app'>
        <div onClick={this.handleClick}
          className={`button ${this.state.active&&'active'}`}>
          click me
        </div>
      </div>
    )
  }
}

export default App
```

视频：state-color-smart
