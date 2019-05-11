### 文件夹和文件(不包含vue文件)

`统一使用小写的英文(符合中文翻译的，不建议直接使用拼音)和中划线组合，不得包含汉子，空格 和 特殊字符`

> 正确示例

```js
文件目录: person-center
脚本文件：config-api.js
样式文件：common-style.css
```
!> 不推荐
```js
文件目录: personCenter
脚本文件：configApi.js
样式文件：commonStyle.css
```

### Vue路由组件
`统一使用英文大驼峰命名`

> 正确示例

```
//个人中心
PersonCenter.vue
```

!> 不推荐

```
//个人中心
personCenter.vue
person-center.vue
```

### HTML命名

`推荐使用HTML5的标签语法`

### JS变量

`统一使用英文小驼峰式 let定义`

> 正确示例

```js
// 变量
let name = 'qui'
let pageNum = '10'
```
!> 不推荐
```js
// 变量
var name = 'qui'
let page_num = '10'
```
### JS常量
`统一使用英文大驼峰式 const定义`

> 正确示例

```js
const Name = 'qui'
const PageNum = '10'
```
!> 不推荐
```js
var Name = 'qui'
let PageNum = '10'
const pageNum = '10'
```
### JS方法函数

`统一使用英文小驼峰式`

> 正确示例

```
myTestFun () {

}
```

!> 不推荐

```
MyTestFun () {

}

my_test_fun () {

}
```
### Css命名

`css命名使用BEM规范, 使用小写加中划线形式`

> 正确示例

```
// 登录按钮
.login-btn {
}
// 登录按钮激活 连接修饰符为--
.login-btn--active {
}
```
!> 不推荐
```
// 登录按钮
.loginBtn {
}
// 登录按钮激活
.loginBtnActive {
}
```

### 图片命名

`使用小写加下划线`

> 正确示例

```
icon_login_bg.png
```
!> 不推荐

```
iconLoginBg.png
icon-login-bg.png
```