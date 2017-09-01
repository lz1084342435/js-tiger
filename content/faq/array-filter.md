filter 的英文本意：筛选。作用就是筛选数组中的元素。

### MDN 官方定义

>
The filter() method creates a new array with all elements that pass the test implemented by the provided function.

翻译：filter() 方法会创建一个由符合传入参数测试的所有元素组成的一个数组。

### 打怪

有数组

```
let a = [3, 4, 21, 11]
```

要数组 b ，所有元素要大于 10 。

### 答案


```js
et a = [1, 2, 3, 12, 34]

let b = a.filter(t => t > 10)
console.log(b)
```

### 另外一个例子

```js
const words = ["spray", "limit", "elite", "exuberant", "destruction", "present"]

const longWords = words.filter(word => word.length > 6)
```

上面的例子会输出所有的字母数大于6的单词组成的数组。
