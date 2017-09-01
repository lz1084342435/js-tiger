一个 *nodejs 项目* 就是：

- 一个文件夹
- 里面有一个 package.json 文件
- `npm install packageName` 就可以安装一个新的 npm 包进来
- 安装的包会存放到 node_modules 文件夹中
- 同时包名会存放到 package.json 文件中
- 一个 nodejs 项目，既可以是后端项目，也可以是前端项目

### 操作步骤

```
mkdir node-demo
cd node-demo
npm init -y
npm install express
```

然后就可以在项目中使用 express 这个包了。
