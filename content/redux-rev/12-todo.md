### 课下作业

实现下面的 TODO 应用：

![](http://digicity-1253322599.costj.myqcloud.com/todo.png)

提示：

- 使用 redux/combineReducers/mapStateToProps 等技术来实现
- 图标可以到  http://www.flaticon.com/ 下载 svg
- 每次点最下面的对勾，只显示已完成事项
- 点对勾右边的列表按钮，显示所有事项

### 第一步

创建一个文件夹，里面写一个 README.md 文件，然后把它上传到 github.com ，使用 create-react-app


- 代码： **create react app**

把所有不用的代码删除：

- 代码： **Hello World**


### 第二步

把各个大块功能合理分层，划分组件，然后页面上不要写内容，但是画出各自所占空间。

- 代码： **Main Layout**

### 写 todo 样式

- 代码：**todo style**
- 代码：**avoid body scroll**
- 已完成条目： **right tick for completed todo**

### form 样式

- **form styling**
- **more form styling**

### actions 样式

- **Actions styling**

### 展示所有的 todo 条目

- **show todoList**

注意：这一步里 Provider 的作用就是要让它所包裹的所有组件中的 mapStateToProps 中可以拿到 store 中的整个状态树，没有 Provider ，mapStateToProps 中的参数 state 就肯定为空了。


### Actions 部分功能

- **actions**


### 添加 todo

- **ADD_TODO**


### 最终代码

- https://github.com/happypeter/todo


### 增强参考

- [更漂亮的一个版本](https://codepen.io/iamjoshellis/pen/zBjEpL)
