# Flux

1 Dispacher

2 action

3 store 每次action都会触发regisiter函数接受的回调 通过waitFor函数确定回调函数执行顺序

4 view初始化用store的数据, 通过action触发数据变动, 通过监听store数据变化的事件来获取最新数据并同步到自己的statezhong

## Flux的优点

1 多层级的组件直接的状态维护变得简单

2 单向数据流 禁止了MVC中View和Model的直接对话

## Flux的不足

1 Store之间的依赖关系

2 难以进行服务端渲染

3 Store混杂了逻辑和状态

# Redux

基本原则

1 单向数据流

2 唯一数据源

3 保持状态可读

4 数据改变只能通过纯函数完成

# 容器组件和傻瓜组件

在Redux框架下,一个React组件基本上就要完成以下两个功能:

1 和Redux Store打交道, 读取Store状态, 用于初始化组件的状态, 同时还要监听Store的状态改变
  当Store状态发生改变时, 需要更新组件状态, 从而驱动组件重新渲染; 当需要更新Store状态时,
  就要派分action对象
2 根据当前props和state, 渲染出用户界面

傻瓜 2 容器 1

# context

通过最外层封装一个组件达到内部组件可以访问的目标

# React-Redux

1 connect

 将Store上的状态转化为props给傻瓜组件(外层的父组件传的prop不用再传一次)
 将傻瓜组件的用户动作转化为派发Store的动作
