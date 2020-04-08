正确地使用 State

1 不要直接修改 State

2 State 的更新可能是异步的（类似e 可以保存在函数内部）(因为 this.props 和 this.state 可能会异步更新，所以你不要依赖他们的值来更新下一个状态)

3 State 的更新会被合并
