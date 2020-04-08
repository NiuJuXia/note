1 在大括号内放置任何有效的 JavaScript 表达式

```js
const name = 'Josh Perez';
const element = <h1>Hello, {name}</h1>;
```

2 在属性中嵌入 JavaScript 表达式时，不要在大括号外面加上引号。

应该仅使用引号（对于字符串值）或大括号（对于表达式）中的一个，

对于同一属性不能同时使用这两种符号。

```js
const element = <div tabIndex="0"></div>; // React DOM 使用 camelCase（小驼峰命名）来定义属性的名称

const element = <img src={user.avatarUrl}></img>;
```
3 假如一个标签里面没有内容，你可以使用 /> 来闭合标签

4 Babel 会把 JSX 转译成一个名为 React.createElement() 函数调用(类似render, 执行后同样生成虚拟DOM)
