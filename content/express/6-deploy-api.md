这集来把前面写好的 API ，部署到公网服务器上（http://express-api.haoqicat.com/）。


### 购买服务器

Peter 用的是 aliyun.com ，也可购买腾讯云。选择 产品 -> 弹性计算 -> 云服务器 ECS 。

系统选择 Ubuntu 。一般一个月100块钱左右。购买后会获得一个公网 IP，例如 182.92.203.18

### 登录服务器

```
ssh root@182.92.203.18
```

然后输入购买的时候，填写的 root 用户密码就可以了。一般上去之后，可以另外创建一个普通用户，例如 peter 。

然后，到自己的域名提供商（ godday.com/万网 )，那里做一个域名指向。例如我把 haoqicat.com 和 182.92.203.18 绑定到一起了。

所以，我就可以这样登录


```
ssh peter@haoqicat.com
```


### 上传代码到 github.com


这样，方便后续服务器上进行持续集成。


### 登录服务器，下载代码


```
ssh haoqicat.com
cd sites
git clone git@github.com:happypeter/express-love-api-demo.git
```

运行 `npm i ` 进行装包，然后，先启动 tmux ，以便维持 `npm start` 进程不死：

```
peter@cat:~/sites/express-love-api-demo/server-api$ npm start

> server-api@1.0.0 start /home/peter/sites/express-love-api-demo/server-api
> node index.js

running on port 5000...
success!
```

现在的问题是，我们这个项目跑到 5000 端口，但是如果我们用 express-api.haoqicat.com 这个域名直接访问服务器，默认是80端口。现在的问题是如何，让指向80端口的访问转到5000端口。


### 配置 nginx 服务器

添加 /etc/nginx/site-enabled/express-love-api.conf 内容如下：


```
server {
    listen     80;
    server_name express-api.haoqicat.com;

    location / {
        proxy_pass http://localhost:5000;
        proxy_set_header X-Forwarded-Proto $scheme;
        proxy_set_header Host $http_x_forwarded_host;
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection "upgrade";
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_read_timeout 3m;
        proxy_send_timeout 3m;
    }
}
```

然后重启 ngnix


```
sudo service nginx reload
```

### 域名指向

现在，要把 express-api.haoqicat.com 指向我们刚刚启动的服务器。


```
ping express-api.haoqicat.com
```
