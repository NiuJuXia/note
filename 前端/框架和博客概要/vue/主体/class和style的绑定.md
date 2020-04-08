```js
//对象方式
<div v-bind:class="classObject"></div>
data: {
  isActive: true,
  error: null
},
computed: {
  classObject: function () {
    return {
      active: this.isActive && !this.error,
      'text-danger': this.error && this.error.type === 'fatal'
    }
  }
}
```

```js
//数组
<div v-bind:class="[{ active: isActive }, errorClass]"></div>
data: {
  activeClass: 'active',
  errorClass: 'text-danger'
}
```

## 用在组件上

当在一个自定义组件上使用 class 属性时，这些 class 将被添加到该组件的根元素上面。这个元素上已经存在的 class 不会被覆盖

内联类似
