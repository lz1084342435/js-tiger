**布局**文件（或者在 React 环境下，我就做成一个布局组件了）它不是一个 React 特有的概念，所有做页面的同学都应该了解这个概念。

一个布局文件，就是一个框框，通常包括 header 和 footer ，但是不包括页面的主体内容。布局文件的作用，如果没有布局文件，那么每个页面中都要专门分别引入 header 和 footer ，代码量会比较大。

下面来看一下，react 环境下如何制作和使用布局文件，英文就叫做 layout file 。


### 总体思路

定以各个页面组件的时候，就不要写 Header 和 Footer 了。例如有下面几个页面

```
ls components/
Home
About
Cart
```

分别代表首页（ Home ），关于 （ About )，购物车（ Cart ）。

然后，App.js 中这样写

```
<Layout>
  <Main />
</Layout>
```

接下来 Main.js 中，写

```
<div className='main'>
  <Home />
</div>
```

这样页面上就可以显示 Home 组件了。

如果要调试 Cart 组件，就把上面的 Home 改成 Cart 。

### 代码

https://github.com/happypeter/mozan/commit/f386221b78f933d99f7b629873fdfd5bbe7972b7

### 视频

http://digicity-1253322599.costj.myqcloud.com/layout.mp4
