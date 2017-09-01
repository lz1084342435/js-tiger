Object.assign 方法用于对象的合并，将源对象（source）的所有可枚举属性，复制到目标对象（target）。


### 例子


```js
var target = { a: 1 };

var source1 = { b: 2 };
var source2 = { c: 3 };

Object.assign(target, source1, source2);
console.log(target) // {a:1, b:2, c:3}
```

上面的例子就是直接合并。

但是如何合并过程中有重复的 key （键），那么后者会覆盖前者。

```js
var target = { a: 1 };

var source1 = { b: 2, c: 2 };
var source2 = { c: 3 };

Object.assign(target, source1, source2);
console.log(target) // {a:1, b:2, c:3}
```
