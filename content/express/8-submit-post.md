本节做发布文章页面

### 写 CSS


- [css for NewPost](https://github.com/happypeter/express-love-api-demo/commit/13595cce4bb74695b5099444a6f453ec46fe00b5)

### 写 NewPost 组件

里面会用到一个 form ，同时这个 form 和未来我们要写的 EditPost 也就是编辑文章的页面的 from 基本上是一样的，所以可以单独抽出来，成为一个 Form 组件，然后复用。


### 自动跳转

发布成功之后自动跳转

```
const NewPost = (props) => {
  const publishPost = (data) => {
    axios.post(`http://express-api.haoqicat.com/post`, data)
    .then(res => {
      console.log(res.data.message)
      props.history.push('/')
    })
  }
  return (
    <div style={styles.content}>
      <div style={styles.title}>写文章</div>
      <Form publishPost={publishPost} label='发布文章' />
    </div>
  )
}
```

上面用的是 `props.history` 这个 prop 只要是被 Router 包裹的组件都有，不一定非要用 withRouter 。


- [submit](https://github.com/happypeter/express-love-api-demo/commit/7a008eefc63cf6edf7949e2dce9f860e7edd1e0f)
- [no need for withRouter](https://github.com/happypeter/express-love-api-demo/commit/7a70e363c460b3ebd9fd986a4add1b4e1889389f)
