不管传入什么类型的值,建议都使用v-bind

单向数据流

1  prop 用来传递一个初始值；这个子组件接下来希望将其作为一个本地的 prop 数据来使用

2  这个 prop 以一种原始的值传入且需要进行转换

有了 inheritAttrs: false 和 $attrs，你就可以手动决定这些 attribute 会被赋予哪个元素（未被组件接受的props默认被挂载在组件根元素上）
