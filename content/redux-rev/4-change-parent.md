简单来说就一句话：

> 通过子组件，修改父组件的 state ，然后把父组件的 state 作为所有子组件的 props 值传入各个子组件

这样就实现了各个兄弟组件间通信。

```js
import React from 'react'

class Child extends React.Component {
  render() {
    return(
      <button onClick={this.props.changeParentState}>Child Button</button>
    )
  }
}

class App extends React.Component {
  constructor() {
    super()
    this.changeBgc = this.changeBgc.bind(this)
  }

  state = {
    color: 'red'
  }

  changeBgc() {
    this.setState({
      color: 'green'
    })
  }
  render() {
    return(
      <div style={{'color': this.state.color}}>
        <div>App</div>
        <Child  changeParentState={this.changeBgc} backGround={this.state.color} />
      </div>
    )
  }
}

export default App

```
