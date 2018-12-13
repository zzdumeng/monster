# vue router

## alias

to use alias,

```js
const router = new Router({
  routes: [
    {
      path: '/settins', component: Settings,
      children: [
        {path: 'profile', component: Profile, alias: ''},
        {path: 'posts', component: Posts},
      ]
    }
  ]
})
```

注意一个路由route必须包含一个component, 否则不能显示,
例如写成下面的形式:

```js
      children: [
        {path: '', alias: 'profile'},
        {path: 'profile', component: Profile},
        {path: 'posts', component: Posts},
      ]
```

那么页面跳转到 `'/settins` 和 `'/settings/profile'` 时, 都是显示的空.
