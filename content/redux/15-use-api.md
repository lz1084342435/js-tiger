# redux-hello 项目联通后台 API

这节来把 redux 代码中的前台假数据都删除，然后从后台 [API](http://redux-hello.haoduoshipin.com/comments) 中把评论读取并显示到前台。

### load comments 读取所有评论

从后台 API 读取评论，相关代码

```js
+import { addComment, fetchComments } from './redux/actions/commentActions'

 class CommentBox extends React.Component {
   constructor() {
@@ -8,6 +8,10 @@ class CommentBox extends React.Component {
     this.handleSubmit = this.handleSubmit.bind(this)
   }

+  componentWillMount() {
+    this.props.fetchComments()
+  }
+
...
+export function fetchComments() {
+  return dispatch => {
+      axios.get('http://redux-hello.haoduoshipin.com/comments').then( response => {
+          dispatch({ type: 'LOAD_COMMENTS', comments: transData(response.data.comments) })
+          // {"msg":"获取成功","comments":[{"_id":"58d88a4d6281635fbed182bd","postId":"1","commentB
+        }
+      )
+  }
+}

switch (action.type) {
  case 'ADD_COMMENT':
    return {...state, [action.postId]: [...state[action.postId], action.comment] }
+    case 'LOAD_COMMENTS':
+      return action.comments
```
