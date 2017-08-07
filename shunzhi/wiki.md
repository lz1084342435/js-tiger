### 总体架构

两个基本元素：人和菜品，很多人因为对菜品的喜爱而进行交流。

所以有：

shunzhi.com/user/happypeter
shunzhi.com/dish/icecream

这是一个社交化的电商系统，所以还是要有购物车的。

要有后台商家系统，可以查看订单，提交新商品。

### 数据可视化

http://recharts.org/#/en-US/examples/TwoSimplePieChart
https://stateofjs.com/2016/fullstack/
http://recharts.org/#/en-US/examples/PieChartWithPaddingAngle
http://jsfiddle.net/2rt6rj2h/?utm_source=website&utm_medium=embed&utm_campaign=2rt6rj2h


### 菜品详情页面

展示一下营养成分和销售额，用 pie/line chart

显示好友点赞评论情况。

一个健康分析按钮，给出健康建议：(用一下加载等待效果)

https://www.zhihu.com/question/22632481

### 个人 Profile

显示好友列表，可以拉黑和添加好友

显示已购菜品，点赞菜品。

拍照上传头像：  (iphone 和 小米微信都测试过了，没有问题)

```
<form>
          <input type="file" accept="image/*" />

  </form>
```

然后服务器端用 https://www.npmjs.com/package/multer

### DashBoard

显示好友点赞，评论情况。没有好友的提示去关注好友。

菜品分类，精品推荐。
