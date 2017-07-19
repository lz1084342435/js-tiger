---
title:  Github Pages 创建个人网站
---

Github.com 是程序员存放代码的一个网站。[Github Pages](https://pages.github.com/) 是 Github 提供的一项服务，可以免费的帮助我们托管网站。

### 注册 Github 账号

点 github.com 首页的 Sign Up （注册）按钮，进行注册。

填写 username （用户名），小写英文字母，不要用空格。

Email 这一项，必须填写真实有效的邮箱，不然注册不了

Choose your personal Plan ?  选择你的付费方案

- 免费版：无限使用权限，只能发布开源项目
- 收费版：允许发布闭源项目


邮箱中点链接之后，就可以自动跳转回 github.com 的页面上，同时显示

>Your email was verified.

你的邮箱已经验证成功了。下一步就可以来创建项目了。

repository （仓库）这个词基本上等价于 project ，差别如下：

```
repository = project + history
```


### 搭建 Github 网站


创建一个仓库，仓库的名字是有严格规定的，

```
username.github.io
```

把 username 替换成自己的自己的用户名。例如我叫 happypeter ，我要创建的仓库名就是

```
happypeter.github.io
```

Description (optional) 项目描述（可选项）

- Public: 开源项目
- Private：闭源项目
- Initialize this repository with a README
  初始化项目的时候，自动添加一个 README 文件

我们这里勾选上这一项。

到达项目页面后，现在来创建一个 index.html ，点 “Create A New File”

添加一些基本的 html 内容进 index.html ，然后点 “Commit New File” 进行保存。

>注意：新添加的内容，不一定立刻能显示到 happypeter.github.io ，可能会有五六分钟的延迟。


### 用 Markdown 来记笔记

Markdown 跟 HTML 一样，是一种标签语言。但是 Markdown 语法特别简单，适合用来做笔记。


- [Markdown 语法参考](https://coding.net/help/doc/project/markdown.html)

Mardown 语法不是浏览器能直接支持的，所以需要先把 Mardown 语法写成的内容，编译成
HTML ，才能美观的显示出来。

那么 Github 就提供了这个编译环境。到 Github 上我们的项目中，有一个文件叫 README.md  这里 md 就是 markdown 的缩写。

在这个文件里面，我们去写 markdown ，就可以翻译成 html 。

例如，我们在 README.md 中填写

```
[百度](http://baidu.com)

<a href="http://baidu.com">百度</a>
```

提交保存之后，页面显示出完全一样的链接效果。

> 注意，添加内容的文件名，无所谓，但是后缀一定要 .md 不然无法编译成功


### Mardown 中添加语法高亮


什么是语法高亮？ 如果一段代码没有语法高亮，那么就是所有的字符都显示成一个颜色。但是通常编辑器中有语法高亮，也就是不同语法作用的字符串会显示成不同的颜色。

markdown 中，如果写成下面这样，最终显示的效果就是有语法高亮的：

    ```js
    console.log('hello');
    console.log('hello');

    console.log('hello');

    console.log('hello');
    ```

    ```css
    body {
      background: red;
    }
    ```

上面的内容会最终显示为：


```js
console.log('hello');
console.log('hello');

console.log('hello');

console.log('hello');
```

```css
body {
  background: red;
}
```

### 如何在 happypeter.github.io 仓库中使用 markdown

在 github pages 项目中使用 markdown ，基本的思路就是

- 如果我想添加一个 pagename.html 的页面
- 那我就创建 pagename.md 这个文件
- 然后里面直接写 markdown 语法就可以了
- 但是，跟普通的 markdown 文件不同，添加到 github pages 页面中的 .md 文件，必须有头部。

头部格式如下：

```
---
title: 我的这篇文章的标题
---
```


### 具体操作步骤

到 happypeter.github.io 的项目仓库中，首先在 index.html 中添加如下内容：

```html
<ul>
  <li>
    <a href="1-first.html">第一篇文章</a>
  </li>
  <li>
    <a href="2-second.html">第二篇文章</a>
  </li>
</ul>
```

然后，就到 https://github.com/happypeter/happypeter.github.io 仓库首页，找到 Create New File 按钮，创建一个新文件，叫做

```
1-first.md
```

里面添加这些内容：

```
---
title: 我的第一篇文章
---

### 第一篇第一个大标题
```

上面`:`后面留一个空格，头部下方留出一个空行，然后再写 markdown 正文

>注意：头部千万不能敲错，不然网站就不更新了。例如，A.md 文件中
头部敲错了，即使后续再创建一个 B.md 文件，里面添加了头部，网站也不会更新。除非先把 A.md 中的头部修改好。

总结一下，虽然很多 github pages 的知识我们还没有介绍，但是有了上面的这些技巧已经完全可以胜任记笔记的工作了。当然如果想让笔记好看，就添加 CSS 进来。










### 更多技巧参考

- [digicity](https://github.com/happypeter/digicity)



# 使用 Gitbook 来做笔记


根据[官网说明](https://github.com/GitbookIO/gitbook/blob/master/docs/setup.md) 第一步，先安装

```
npm install gitbook-cli -g
```


然后，创建一个笔记文件夹

```
mkdir my-note
```

然后执行

```
cd my-note
gitbook init
```

这样，可以生成两个文件

- README.md 的内容会显示在书皮上
- SUMMARY.md 是目录

### 启动服务器，查看和编辑书籍


```
gitbook serve
```

这样，可以启动一个服务器，然后到 localhost:4000 端口，就可以看到这本书了。

可以修改 SUMMARY.md 来添加书籍目录

```
# Summary

* [Introduction](README.md)
* [第一章：redux](./redux/index.md)
  * [第一节：state 复习](./redux/1-state.md)
  * [第二节：你好 redux](./redux/2-hello-redux.md)
```

下一步，创建笔记文件，atom 到 redux 文件夹中创建 1-state.md 和 2-hello-redux.md 文件。


### 保存书稿到 github 仓库

首先到 github.com 上创建 my-note 仓库。

运行 gitbook serve 命令之后，生成临时文件夹 `_book` 这个不是我们写的，所以一定要放到 .gitignore 文件中，所以，我们就在 my-note 文件夹的顶级位置，创建 .gitignore 文件，内容如下

```
_book
node_modules
```

接下来我们想做的事情是：把书稿上传到 github.com/happypeter/my-note 这个仓库的 master 分支保存起来。具体步骤是：

```
cd my-note
git init
git add -A
git commit -m"msg"
git remote add origin git@github.com:happypeter/peter-note.git
git push -u origin master
```

最终达成的效果，就是访问 https://github.com/happypeter/my-note 就可以看到书的原稿了。

新系统会遇到 ssh key 相关的问题，这个可以参考本书对应的 github.com 章节。

### 托管我的 gitbook

为了部署方便，我们把我们的 my-note 的内容结构稍微调整一下，把原有的所有的笔记都放到 content 文件夹中，也就是有这样的目录结构

```
cd my-note
cd content
ls
README.md  SUMMARY.md redux
```

为何要把内容都统一放到 content 文件夹呢？答案就是，托管到 github 上的内容，其实是一个**编译后** 的内容，而不是原始内容。现在我们把原始内容都放到 content 文件夹中，未来会把编译输出内容放到 my-note/gh-pages 文件夹中。

### 添加自动化脚本

上面的操作之后，如果我们再去运行：

```
gitbook serve
```

就会报错，因为文件找不着了。需要把命令改一下

```
gitbook serve ./content ./gh-pages
```

这样，我们就又可以启动成功了，同时，也会自动创建 gh-pages 文件夹，文件夹中的内容，就是编译后的输出。

每次启动的时候，都要敲长长的命令，很不方便，所以，我们就需要把命名简短化，具体就是去写成 **npm 脚本**。具体步骤如下：

第一步，把项目变成一个 nodejs 的项目：

```
cd my-note
npm init -y
```

然后，package.json 中添加这些代码：

```json
"scripts": {
 "start": "gitbook serve ./content ./gh-pages"
},
```

有了上面的 npm 脚本之后，我们如果我想在本地 4000 端口查看本书，只需要运行

```
npm start
```

就可以成功预览了。

注意，此时多个一个文件夹 gh-pages，这个文件夹中的内容，也不是我们自己写的，所以到 .gitignore 文件里面添加

```
gh-pages
```

然后再进行 git 做版本的操作。

### 部署书籍到 gh-pages

这一步，可以手动做：

- 第一步：编译项目，来把 md 文件翻译成 html 放到 gh-pages 文件夹
- 第二步，拷贝 gh-pages 中的所有文件，到本仓库的 gh-pages 分支，然后上传
- 第三步，以后每次修改完都需要拷贝到 gh-pages 分支，很麻烦

所以，我们采用一个 npm 包，来帮助我们完成上面的操作

```
cd my-note/
npm i --save gh-pages
```

然后创建 my-note/scripts/deploy-gh-pages.js

里面的内容是：

```
'use strict';

var ghpages = require('gh-pages');

main();

function main() {
    ghpages.publish('./gh-pages', console.error.bind(console));
}
```

上面的脚本的作用，就是把当前文件夹下的 gh-pages 文件夹中的所有内容，push 到本仓库的 gh-pages 分支。

然后添加一个 npm 脚本 `deploy` （ deploy 就是部署的意思），如下：

```json
"scripts": {
 "start": "gitbook serve ./content ./gh-pages",
 "deploy": "node ./scripts/deploy-gh-pages.js",
},
```

那么，可以来试试，保证 `npm start` 处于运行中的状态，然后运行

```
npm run deploy
```

注：如果最后返回 `undefined` 字样，表示没有出现错误，部署成功。

就可以把编译后的书稿 push 到远端仓库的 gh-pages 分支了。也就是可以到 https://happypeter.github.io/my-note 这个链接，看到书了。

这样，大功告成。
