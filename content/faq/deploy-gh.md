基本上就是按照 create-react-app 给的提示做即可。


### 具体步骤

先创建本地项目

```
create-react-app ccc
```

然后到 github.com 上创建同名项目 ccc ，将本地项目上传到 ccc 。


运行

```
npm run build
```

根据提示信息，我需要往 package.json 文件中添加

```
  "homepage": "http://happypeter.github.io/ccc",
```

再次运行 `npm run build`，根据提示信息，安装 gh-pages 这个包

```
npm i gh-pages
```


然后到 scirpts 标签内，添加

```
    "deploy": "gh-pages -d build"
```



这样就一切 OK ，最终的 package.json 如下：

```json
{
  "name": "ccc",
  "version": "0.1.0",
  "homepage": "http://happypeter.github.io/ccc",
  "private": true,
  "dependencies": {
    "gh-pages": "^1.0.0",
    "react": "^15.6.1",
    "react-dom": "^15.6.1",
    "react-scripts": "1.0.13"
  },
  "scripts": {
    "start": "react-scripts start",
    "build": "react-scripts build",
    "test": "react-scripts test --env=jsdom",
    "eject": "react-scripts eject",
    "deploy": "gh-pages -d build"
  }
}
```



### 每次修改完

先运行

```
npm run build
```

然后

```
npm run deploy
```

注意：deploy 有时候需要等一会儿，页面上才能看到更新

https://happypeter.github.io/ddd/


### 视频

http://digicity-1253322599.costj.myqcloud.com/deploy-gh.mp4
