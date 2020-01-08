# 划分组件边界的原则

拆分组件最关键的就是确定组件的边界,每个组件都应该是可以独立存在的,如果两个组件逻辑太紧无法清晰定义各自的责任,不拆分可能更好。

# React组件的数据

对外使用prop, 内部用state

当prop的类型不是字符串时,必须用{}包裹住

propTypes 接口检查(babel-react-optimize)

defaultProps

state

修改使用setState,传入对象或函数(如果依赖当前state或props建议使用函数)

# 组件的生命周期

## 装载过程

1 constructor

目的 初始state 绑定成员函数的this环境

2 getIntialState和getDefaultProps(废弃)

3 render

如果不需要渲染DOM就返回null或false

4 componentWillMount 和 componentDidMount

分别在render函数前后,componentDidMount被调用时组件已经被装载到DOM树上了


