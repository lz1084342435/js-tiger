# redux-hello 项目联通后台 API


这节来把 redux 代码中的前台假数据都删除，然后从后台 [API](http://redux-hello.haoduoshipin.com/comments) 中把评论读取并显示到前台。




# 以下是老笔记内容


### 后台 API

### 实现 axios 异步操作
### 实现 axios 读取后台评论操作

要求，store 中的死数据（仅限于评论）全部删除，从后台读取，加载到页面上。每篇文章各自显示自己的评论。

难点：后端得到的数据，跟我们前端需要的格式有差异，需要用代码调整一下数据格式。

参考：

如何从服务器加载数据到 redux 中，参考：https://github.com/happypeter/hand-in-hand-react-demo/blob/master/client/complete/src/ui/DashBoard.js#L11

代码：

- [load data from server OK](https://github.com/happypeter/redux-hello/commit/3305ae8cf37dc8c46c535091e2264e1a8eedb13b) 调整了 action ，成功的从服务器端获取了所有评论，并显示到了页面上。

现在面临的任务就是数据的整理了：

要把服务器返回的

```
{"_id":"58d88a4d6281635fbed182bd","postId":"1","commentBody":"hello1","__v":0},{"_id":"58d88b8b17deb3614c29065f","postId":"2","commentBody":"hello2","__v":0}
```

整理成下面的格式：

```
let comments = {
  1: ['nice course', 'help me a lot'],
  2: ['really good', 'save me lots of time']
}
```


解决方案如下：

```
let cc = [
  { _id: '58d88a4d6281635fbed182bd',
    postId: '1',
    commentBody: 'hello1',
    __v: 0 },
  { _id: '58d88b8b17deb3614c29065f',
    postId: '2',
    commentBody: 'hello2',
    __v: 0 },
  { _id: '98d88a4d6281635fbed182bd',
    postId: '1',
    commentBody: 'hello11',
    __v: 0 },
  { _id: '58d8bf1317deb3614c290660',
    postId: '2',
    commentBody: 'hello22',
    __v: 0 }
]

let post1Com  = cc.filter(value => value.postId != '2' ).map(item => {
  return item.commentBody;
})

let post2Com = cc.filter(value => value.postId != '1' ).map(item => {
  return item.commentBody;
});
console.log(post1Com, post2Com);
// [ 'hello1', 'hello11' ] [ 'hello2', 'hello22' ]
```


继续上代码：

- [data format change](https://github.com/happypeter/redux-hello/commit/ed7316ea044bedb7b37e3d48c923085fdf31a08b) 这个最终实现了数据格式的转换
- [bring commentList back](https://github.com/happypeter/redux-hello/commit/1852f67ee5d0c1bdb94db8f571947d4d63fc20bb) 页面重新正常显示评论
