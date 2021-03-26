# v3render

## setup() 的作用
提供响应式数据

## render() 获取 setup() 中的数据
setup() 方法中 return 出去的数据, 会绑定在 this 上, 在render() 中可以通过 this 获取

## render() 中需要修改 setup() 中的数据, 怎么样才能实现双向绑定
1. render() 中直接修改 this 之中拿下来的数据, 就可以实现双向绑定
2. 在 setup() 之中创建修改变量的方法, render 通过 this 获取到

> 坑记: 第24行, 如果将 todoItemValue 重新赋值, 就会失去响应式