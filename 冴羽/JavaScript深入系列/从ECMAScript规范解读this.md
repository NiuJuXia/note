# JavaScript深入之从ECMAScript规范解读this

ECMAScript 的类型分为语言类型和规范类型。

## Reference

 Reference 的构成，由三个组成部分，分别是：

* base value
* referenced name
* strict reference

```js
var foo = 1;

// 对应的Reference是：
var fooReference = {
    base: EnvironmentRecord,
    name: 'foo',
    strict: false
};
```

再举个例子：

```js
var foo = {
    bar: function () {
        return this;
    }
};
 
foo.bar(); // foo

// bar对应的Reference是：
var BarReference = {
    base: foo,
    propertyName: 'bar',
    strict: false
};
```

而且规范中还提供了获取 Reference 组成部分的方法，比如 GetBase 和 IsPropertyReference。

这两个方法很简单，简单看一看：

1.GetBase

>GetBase(V). Returns the base value component of the reference V.

返回 reference 的 base value。

2.IsPropertyReference

>IsPropertyReference(V). Returns true if either the base value is an object or HasPrimitiveBase(V) is true; otherwise returns false.

简单的理解：如果 base value 是一个对象，就返回true。

## GetValue

除此之外，紧接着在 8.7.1 章规范中就讲了一个用于从 Reference 类型获取对应值的方法： GetValue。

简单模拟 GetValue 的使用：

```js
var foo = 1;

var fooReference = {
    base: EnvironmentRecord,
    name: 'foo',
    strict: false
};

GetValue(fooReference) // 1;
```

GetValue 返回对象属性真正的值，但是要注意：

**调用 GetValue，返回的将是具体的值，而不再是一个 Reference**

这个很重要，这个很重要，这个很重要。

## 如何确定this的值

1.计算 MemberExpression 的结果赋值给 ref

2.判断 ref 是不是一个 Reference 类型

    2.1 如果 ref 是 Reference，并且 IsPropertyReference(ref) 是 true, 那么 this 的值为 GetBase(ref)

    2.2 如果 ref 是 Reference，并且 base value 值是 Environment Record, 那么this的值为 ImplicitThisValue(ref)

    2.3 如果 ref 不是 Reference，那么 this 的值为 undefined

简单理解 MemberExpression 其实就是()左边的部分。

this 为 undefined，非严格模式下，this 的值为 undefined 的时候，其值会被隐式转换为全局对象

```js

var value = 1;

var foo = {
  value: 2,
  bar: function () {
    return this.value;
  }
}

//示例1
console.log(foo.bar()); // 2
//示例2
console.log((foo.bar)()); // 2
//示例3
console.log((foo.bar = foo.bar)()); // 1
//示例4
console.log((false || foo.bar)()); // 1
//示例5
console.log((foo.bar, foo.bar)()); // 1

```
