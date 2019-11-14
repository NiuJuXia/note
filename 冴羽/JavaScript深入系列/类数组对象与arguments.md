# JavaScript深入之类数组对象与arguments

## 类数组对象

所谓的类数组对象:

>拥有一个 length 属性和若干索引属性的对象

```js
var array = ['name', 'age', 'sex'];

var arrayLike = {
    0: 'name',
    1: 'age',
    2: 'sex',
    length: 3
}
```

Array.from(arrayLike)

[...arguments]

传入的参数，实参和 arguments 的值会共享，当没有传入时，实参与 arguments 值不会共享

除此之外，以上是在非严格模式下，如果是在严格模式下，实参和 arguments 是不会共享的。

