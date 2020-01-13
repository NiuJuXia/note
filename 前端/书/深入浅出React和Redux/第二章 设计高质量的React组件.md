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

生命周期函数是指组件在某一时刻自动调用的函数

## 装载过程

1 constructor

目的 初始state 绑定成员函数的this环境

2 getIntialState和getDefaultProps(废弃)

3 render

如果不需要渲染DOM就返回null或false

4 componentWillMount 和 componentDidMount

分别在render函数前后,componentDidMount被调用时组件已经被装载到DOM树上了

## 更新过程

1 componentWillReceiveProps(nextProps)

当父组件的render函数被调用,在render函数里面被渲染的子组件就会经历更新过程,触发此函数

2 shouldComponentUpdate(nextProps, nextState)

返回一个布尔值,告诉React是否继续更新

在以上两个函数中,函数内部可以用this.props和this.status取得之前的值

3 componentWillUpdate和componentDidUpdate

分别在render函数前后

## 卸载过程

componentWillUnmount

# 组件向外传递数据

通过函数参数传递



