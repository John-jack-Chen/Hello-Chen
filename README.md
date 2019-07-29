# vue-admin-template
vue轻量级后台管理系统基础模板<br>

`icon`使用的是`iview`组件的`icon`组件。

数据格式：
```js
// 左侧菜单栏数据
menuItems: [
    {
        name: 'Home', // 要跳转的路由名称 不是路径
        size: 18, // icon大小 非必填
        type: 'md-home', // icon类型 非必填
        text: '主页' // 文本内容
    },
    {
        text: '二级菜单',
        type: 'ios-paper',
        children: [
            {
                type: 'ios-grid',
                name: 'T1',
                text: '表格'
            },
            {
                text: '三级菜单',
                type: 'ios-paper',
                children: [
                    {
                        type: 'ios-notifications-outline',
                        name: 'Msg',
                        text: '查看消息'
                    },
                    {
                        type: 'md-lock',
                        name: 'Password',
                        text: '修改密码'
                    },
                    {
                        type: 'md-person',
                        name: 'UserInfo',
                        text: '基本资料',
                    }
                ]
            }
        ]
    }
]
```
## 相关依赖
* [vue-router](https://router.vuejs.org/zh/)
* [iview](https://www.iviewui.com/docs/guide/install)
* [axios](https://www.kancloud.cn/yunye/axios/234845)
* [vuex](https://vuex.vuejs.org/zh/)

## 功能

#### 登录页


#### 标签栏


**注意：** 组件的名称和路由的名称一定要一致，例如 `Home.vue` 组件名称 `name: home`，则在路由文件中也要给它设置为 `name: home`，否则页面内容不能缓存

```js
// 在router文件中
{
    path: 'home',
    name: 'home',
    component: () => import('../views/Home.vue')
}

// 在Home.vue中
export default {
    name: 'home'
}
```

#### 侧边栏
* 伸展/收缩
* 页面宽度过小自动收缩
* 多级菜单（利用iView组件）

#### 用户相关
* 消息通知
* 用户头像
* 基本资料

#### 动态菜单栏
* 根据数据动态生成菜单

#### 面包屑
* 展示当前页面的路径

#### 权限控制
* 如果在未登陆的情况下访问指定页面 将会重定向到登陆页

#### 其它
* 利用`axios`拦截器 实现了`ajax`请求前展示`loading` 请求结束关闭`loading`

## 注意
* 源码可见 并且添加了必要的注释 可以自行更改


`Index`组件一般情况下只需要传数据就行 其他不用关注

市面上有大量的vue后台管理系统模板 但是功能都太丰富了 而且有很多组件用不上 所以写了这么一个最基础的 只有必要功能的模板
UI库使用的是`iView` 有大量的组件可用 

### 子组件跳转到子组件
```
// xxx为你想跳转的子组件name
this.$parent.gotoPage('xxx')
```
### 路由传参
```
this.gotoPage('userinfo', {
    id: id,
})
// 在userinfo组件里取参
this.$route.params.id
```

## 使用
#### 下载
```
git clone https://github.com/John-jack-Chen/Hello-Chen.git

cd vue-admin-template

npm i
```

#### 开发
```
npm run serve
```

#### 打包
````
npm run build
````


### 如果对你有帮助，请给个Star
