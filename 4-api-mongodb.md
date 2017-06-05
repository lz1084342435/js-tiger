这节我们来实现 API ，用户从客户端，调用 API ，就可以读写数据库中的文章。


### 定义读操作 API 路由

读操作，一般用 GET 方法，所有博客，英文叫 `posts` ，所以这个 API 的路由就要写成

```
app.get('/posts', function() {
  ....
  })
```

### 回调中，写 mongoose 语句

API 的实现如下：

```
app.get('/posts', (req, res) => {
  console.log('GET /posts........')
  Post.find().sort({'createdAt': -1}).exec(function(err, posts) {
    if (err) return res.status(500).json({error: err.message});
    res.json({ posts })
  });
})
```

上面的 API 会等待客户端的 GET /posts 请求，一旦收到请求，首先打印 `GET /posts...` ，然后去进行数据库的读取操作，读到所有的文章内容，存到  posts 变量中，
然后，通过 res.json 语句，把数据以 JSON 的格式反馈给客户端，供前端开发者使用。


### 实现写操作的 API

根据 HTTP 协议，写操作一般用哪个动词（方法）呢？用 POST 。所以我们的 API 路由要写成

```
app.post('/post/:id', (req) => {
  console.log('POST /post/:id', req.params.id)
})
```


有了上面的代码，然后就可以从客户端发请求了。我们先用 curl 来模拟一下客户端代码：


```
curl -X POST 'http://localhost:5000/post/3'
```

上面：

- `-X` 是设置选项，选项的值是 POST


### 传递复杂数据


通常如果用 axios 发送 POST 请求，发送的数据格式为 JSON ，可以用下面的 curl 命令来模拟：

```
curl -H "Content-Type: application/json" -X POST -d '{"title":"happypeter"}' http://localhost:5000/post
```

上面:

  - `-H` 选项后面跟的是 HTTP 报头，设置数据格式为 json
  - `-d` 后面跟的是负载数据( payload )


服务器端如果要接受这些数据，需要再专门安装一个包：

```
npm i --save body-parser
```

然后添加如下代码：


```
var bodyParser = require('body-parser');
...
app.use(bodyParser.json());
```


这样，如果我的 API 写成这样


```
app.post('/post', (req, res) => {
  console.log(`POST /post`, req.body)
  var post = new Post(req.body);
  post.save(function(err){
    if(err) console.log(err);
  })
} )
```

就可以把客户端传递过来的数据，保存到数据库了。
