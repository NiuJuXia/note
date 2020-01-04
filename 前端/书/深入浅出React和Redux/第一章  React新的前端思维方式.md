## React（Reactive Programming 响应式编程）

>create-react-app [name]

>组件:完成某个特定功能的独立的,可复用的代码(可复用或本身较为复杂将其拆出来)

>使用JSX必须要有React

## HTML的onclick

1 onclick添加的事件处理函数是在全局环境下执行的,这污染了全局环境,很容易产生意料不到的后果;

2 给很多DOM元素添加onclick事件,可能影响性能;

3 动态删除DOM元素,忘记注销事件处理器,可能造成内存泄漏

## React的onClick

1 使用了事件委托;

2 在事件生命周期中可以去除;

3 每个函数都在组件范围内

## React理念

UI = render(data)

Virtual DOM: DOM树是对HTML的抽象  Virtual DOM 是DOM树的抽象


