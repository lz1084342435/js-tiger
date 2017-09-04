```js
import React, { Component } from 'react'
import './app.css'

class App extends Component {

  state = {
    comments: [
      {
        name: 'peter',
        text: '你好'
      },
      {
        name: 'billie',
        text: 'Hi'
      }
    ]
  }


  render () {
    const list = this.state.comments.map((item, i) => (
      <li key={i}>{`${item.name}: ${item.text}`}</li>
    ))
    return (
      <ul className='app'>
        {list}
      </ul>
    )
  }
}

export default App
```
