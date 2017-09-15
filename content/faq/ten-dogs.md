来做一个案例：一个页面上显示十个小狗图片，鼠标滑过一个图片，显示删除按钮，可以删除图片。页面上另外有一个加号，可以用来添加小狗图片。点加号显示一个只有一个 input 的表单，里面添加 imgUrl 。
每个图片点进去，可以查看该狗狗的详细介绍，并且这个介绍内容，是可以修改的。

修改效果参考：https://github.com/happypeter/dj-demos/issues/13


### 步骤一：路由和布局

视频：http://digicity-1253322599.costj.myqcloud.com/dog1-layout.mp4
视频：http://digicity-1253322599.costj.myqcloud.com/dog2-layout-css.mp4

### 步骤二：显示十个小狗

视频：http://digicity-1253322599.costj.myqcloud.com/dog3-dog-list.mp4


### 步骤三：搭建 API

视频 http://digicity-1253322599.costj.myqcloud.com/dog4-api.mp4

创建 package.json 的命令

```
npm init -y
```

确认 API 有没有正常运行，就到浏览器访问

http://localhost:3008/dogs

能看到数据证明 API 运行起来了。


代码：https://github.com/happypeter/dj-demos/commit/e627340aba53409f1d6e8939ca257f8cd07db340

### 步骤四：添加小狗的前端样式

dog5-form-css

### 步骤五：添加小狗

提交数据到服务器端的数据库，要 axios 请求。

视频：dog6-form-submit

注意：在发 axios 请求的时候，数据是有格式。

```
const data = {
  imgUrl: 'xxxx.jpg'
}

axios.get('http://localhost:3008/posts', data)
```

视频：http://digicity-1253322599.costj.myqcloud.com/dog7-state.mp4



视频 http://digicity-1253322599.costj.myqcloud.com/dog8-trim.mp4

### 步骤六：删除小狗

http://digicity-1253322599.costj.myqcloud.com/dog9-delete.mp4

### 步骤七：显示小狗详情

http://digicity-1253322599.costj.myqcloud.com/dog10-detail.mp4

- https://github.com/happypeter/dj-demos/tree/master/ten-dogs
