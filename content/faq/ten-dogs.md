来做一个案例：一个页面上显示十个小狗图片，鼠标滑过一个图片，显示删除按钮，可以删除图片。页面上另外有一个加号，可以用来添加小狗图片。点加号显示一个只有一个 input 的表单，里面添加 imgUrl 。
每个图片点进去，可以查看该狗狗的详细介绍，并且这个介绍内容，是可以修改的。

修改效果参考：https://github.com/happypeter/dj-demos/issues/13


### 难点一：如果向 json-server 数据库中存入数据

db.json 写成这样

```json
{
  "dogs": []
}
```


然后，写一个 Form.js 组件


```js

handleSubmit = () => {
  let data = {
    imgUrl: 'https://ss3.bdstatic.com/70cFv8Sh_Q1YnxGkpoWK1HF6hhy/it/u=734972231,2892744574&fm=27&gp=0.jpg'
  }
  axios.post('http://localhost:3008/dogs', data).then(
    res => {
      console.log(res.data)
    }
  )
  console.log(this.state)

}
```

### 代码

- https://github.com/happypeter/dj-demos/tree/master/ten-dogs
