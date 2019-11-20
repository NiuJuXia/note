# JavaScript深入之call和apply的模拟实现

>call() 方法在使用一个指定的 this 值和若干个指定的参数值的前提下调用某个函数或方法。

模仿步骤
1:将函数设为对象的属性
2:执行该函数
3:删除该函数
4:导参
5:this 参数可以传 null，当为 null 的时候，视为指向 window
6:函数是可以有返回值的！
```js
Function.prototype.call2 = function(context,...less) {
  var context = context || window;
  context.fn = this;
  var result=context.fn(...less);
  delete context.fn;
  return   result
}
```
