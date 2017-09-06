来对前面讲过的知识点：

- 数组和 key
- 事件响应函数中传参数

综合运用一下。


# 打怪

给出一个列表，显示出各种衣服尺码

```
M L XL XXL
```

让用户可以去选择一个尺码。

### 答案

```js
import React, { Component } from 'react'
import './app.css'

class App extends Component {
  state = {
    activeIndex: 0,
    sizes: [
      {
        size: 'X'
      },
      {
        size: 'XL'
      },
      {
        size: 'XXL'
      }
    ]
  }

  handleClick = (i) => {
    console.log(i)
    this.setState({
      activeIndex: i
    })
  }

  render () {

    const list = this.state.sizes.map((t, i) => (
      <div onClick={() => this.handleClick(i)}
        className={`size ${this.state.activeIndex===i&& 'active'}`}
        key={i}>{t.size}</div>
    ))
    return (
      <div className='app'>
        {list}
      </div>
    )
  }
}

export default App
```


### 代码

list-mani

### 视频

list-select
