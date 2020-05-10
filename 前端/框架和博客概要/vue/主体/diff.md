##一

第一个参数不是vnode 会创建一个空的vnode作为oldvnode

如果是相同的vnode(key tag) 执行函数二

不同 删掉重建

## 二

设置新的vnode的el(同旧的一样)

获取新旧的children

根据是否有新的是否有children

新旧都有children(执行函数三) 新有旧无 新无旧有 新旧全无

## 三

优化(头头比 尾尾比...)新旧children是否为同一个 是就执行第二个函数

都未命中 拿新节点的key与旧对比 ...


