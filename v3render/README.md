v3render

## render 实现
### setup() 的作用
提供响应式数据
> setup() 中也可以返回 h 函数, ~~但似乎无法响应式, 代码参考 test.vue, 猜测：return () => h() 只会执行一次~~
```jsx
setup(){
  return () => h()
}
```

### render() 获取 setup() 中的数据
setup() 方法中 return 出去的数据, 会绑定在 this 上, 在render() 中可以通过 this 获取

### render() 中需要修改 setup() 中的数据, 怎么样才能实现双向绑定
1. render() 中直接修改 this 之中拿下来的数据, 就可以实现双向绑定
2. 在 setup() 之中创建修改变量的方法, render 通过 this 获取到

> 坑记: 第24行, 如果将 todoItemValue 重新赋值, 就会失去响应式


## JSX 实现

### 安装插件
安装[Babel 插件](https://github.com/vuejs/jsx-next)
---
Install the plugin with:
`npm install @vue/babel-plugin-jsx -D`
Then add the plugin to .babelrc:
```json
{
  "plugins": ["@vue/babel-plugin-jsx"]
}
```
> 如果是 `babel.config.js`, 去掉双引号
> vue 文件需申明 `<script lang="tsx">`

### setup() 返回渲染函数
[参考文档](https://v3.cn.vuejs.org/guide/composition-api-setup.html#%E4%BD%BF%E7%94%A8%E6%B8%B2%E6%9F%93%E5%87%BD%E6%95%B0)


### 为什么 <li onClick={() => handlerItemClick(index)}
