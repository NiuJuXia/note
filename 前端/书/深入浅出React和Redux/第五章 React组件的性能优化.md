# React组件的性能优化

## 单个React组件的性能优化

  当组件数据更新时, 组件内部的子组件的render也将被调用,可以使用例如
  
 ```js
  shouldComponentUpdate(nextProps, nextState) {
    return (nextProps.completed !== this.props.completed) || ......
  }
  ```
  
  在react-redux中自带的shouldComponentUpdate函数是`浅层比较`,也就是说即使对象内容完全一样，只要不是同一个对象的引用,也会被认为是不同的对象。
  
  尤其需要注意的是带参数的函数
  
  1 将函数和参数分别传入
  
  2 在子组件创建使用函数
  
  ## 多个React组件的性能优化
  
  # React的调和过程（更新前后的Virtual DOM的找不同）
  
  1 节点类型不同的情况
  
  如果根节点改变, 则原组件被卸载, 一切重来.
  
  所以一定要避免作为包裹功能的节点类型被随意更改。
  
  2 节点类型相同的情况
  
  只改变改变的属性
  
  3 多个子组件
  
  插入最后一项
  
  全部更新, 但使用shouldComponentUpdate函数可以避免实质更新
  
  插入第一项
  
  直接挨个比较
  
  方法(key)这样就只会进行更新, 可以使用shouldComponentUpdate函数可以避免实质更新
  
  ## 用reselect提高数据获取性能
  
  # 两阶段的选择过程
  
  第一步接受一个数组，对于需要观察的数据的函数
  
  第二步操作
  
  达到类似vue computed缓存的效果
  
  # 范式化状态树
  
  ```js
  
  {
    id:1,
    text:'待办事项一',
    completed:false,
    typeid:1
    }
    {
      id:1,
      name:'紧急',
      color:'red'
    }
  ```
  
  
  
  
  
  
