# vuex

## module

当使用 `namespaced` 为`true` 时, 需要注意的是
对于 `state`, 已经默认是添加了namespace,
而对于`mutation`, `action`, 和 `getters`, 都是以slash分隔开的.

i.e.

```js
new Store({
  modules: {
    account: {
      namespaced: true,
      state: {
        name: ''
      },
      mutations: {
        change(state) {

        }
      }
    }
  }
})
{

  state: {}
}
```

在组件内使用时, 对state就不能在`mapState`中使用字符串的形式,
而要写成函数的形式.

```js
{

computed: {
  ...mapState({name: state => state.account.name})
},
methods: {
  ...mapMutations({change: 'account/change'})
}
}
```
