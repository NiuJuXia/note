# JavaScript深入之bind的模拟实现

bind() 方法会创建一个新函数。当这个新函数被调用时，bind() 的第一个参数将作为它运行时的 this，之后的一序列参数将会在传递的实参前传入作为它的参数。

1:返回一个函数
2:可以传入参数
3:传入参数(保存参数)
4:一个绑定函数也能使用new操作符创建对象：这种行为就像把原函数当成构造器。（注意原型的传递）
5：提供的 this 值被忽略，同时调用时的参数被提供给模拟函数。
```js
Function.prototype.bind2 = function (context,...next1) {
    var self = this;
    var fNOP = function () {};
    var fBound = function (...next2) {
      let next3=next1.concat(next2)
        return self.apply(this instanceof fBound ? this : context,next3);
    }
    fNOP.prototype = this.prototype;
     fBound.prototype = new fNOP();
     return fBound;
}
```
