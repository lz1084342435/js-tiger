任务要求：

- 写一个静态的 html 页面
- 可以到 username.github.io/project 下面访问到

### 具体步骤

首先确定能不能往 github 仓库中推送文件？( ssh-key 要提前加好)。 然后到 github.com 创建 dj-demos 仓库。


接下来，本地创建同名项目

```
mkdir dj-demos
cd dj-demos
git init
atom index.html README.md
git add -A
git commit -m"msg"
git remote add origin git@github.com:happypeter/dj-demos.git
git push -u origin master
```

但是，页面放到 master 分支，是不能显示到 happypeter.github.io/dj-demos 这个位置的。需要创建 gh-pages 分支

```
git checkout -b gh-pages
```

上面操作的，其实是拷贝了当前的 master 分支，也就是所有的 master 分支上的文件，在 gh-pages 分支上也有。

就是把本地 gh-pages 分支内容，上传到 github.com

```
git push -u origin gh-pages
```

等待一会儿，就可以到  https://happypeter.github.io/dj-demo 下看到网页了。

### 视频

http://digicity-1253322599.costj.myqcloud.com/deploy-gh.mp4
