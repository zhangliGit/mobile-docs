### 文件注释说明

`所有文件,包括vue文件,js文件,css文件等需要在头部标注注释说明`

```js
/**
 * @description 接口API配置文件    // 文件描述
 * @author zhangli <zl@xx.com>    // 创建人
 * @date 2018/07/26     // 创建时间
 * @update 新增个人中心接口  hj<hejin@xx.com> 2019/04/15
 */
```
### JS注释

`单行注释`

```js
// 定义初始用户名
let name = 'qui'
```
`多行注释`

```js
/**
 * 定义初始用户名
 * 缓存备用
 */
let name = 'qui'
```

`函数方法注释`

```js
<script>
export default {
  name: 'app',
  methods: {
      /**
       * @description 获取用户openId
       * @param {Nunber} uId 用户id
       * @param {Stirng} uName 用户姓名
       */
      getOpenId (uId, uName) {

      }
  }
}
</script>
```

!> 避免盲目的注释，否则适得其反

### Html注释

`尽量避免使用Html注释`

### Css注释

`在公用的css文件中对不同模块样式代码块进行注释`

```js
/* 登录 */
.login {

}

/* 提示框样式*/
.toast {

}
```

### 代码缩进，引号，分号

`html,js,css代码统一使用2个空格缩进`

`html中引号使用双引号，js中使用单引号`

`js代码中不使用分号;结尾`
```js
*ESLint规则:
"quotes": [1, "single", "avoid-escape"], // 引号风格
"comma-dangle": ["error", "never"], // 紧张对象中出现结尾逗号
```

```js
<template>
  <div id="app">
    <div class="login-name">
      qui
    </div>
  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      name: 'qui'
    }
  },
  methods: {
    getName () {
      let title = 'qui'
      alert(title)
    }
  }
}
</script>

<style lang="less" scoped>
  .login-name {
     color: red;
  }
</style>
```

### 代码空格

`=等号左右两侧都需要一个空格`

> 正确示例

``` js
let name = 'qui'
```
!> 不推荐

```
let name='qui'
```

`()括号左右两侧都需要一个空格`
```js
*ESLint规则:
"space-before-blocks": [2, "always"], // 块前的空格
```

> 正确示例

```js
function myFun () {

}
let myFun = () => {

}
```
!> 不推荐

```
function myFun(){

}
let myFun =()=> {

}
```

`{}大括号左侧或右侧需要一个空格`

> 正确示例

```js
if (true) {

} else {

}
```

!> 不推荐

```js
if (true){

}else{

}
```

### JavaScript规范

`判断是否相等时使用严格等号或不等号`
```js
*ESlint 规则:  
"eqeqeq": ["error", "smart"],  // 比较的时候使用严格等于
```
> 正确示例

```js
if (true === 1) {

}
if (ture !== 1) {

}
```

!> 不推荐

```js
if (true == 1) {

}
if (ture != 1) {

}
```

`代码中不要出现连续的多行空行`
```js
*ESLint规则: "no-multiple-empty-lines": [2, {"max": 1}], // 空行最多不能超过一行
```
> 正确示例

```js
export default {
  name: 'app',
  data () {
    return {
    }
  },
  methods: {
    getData () {
      let name = 'qui'
      console.log(name)
    }
  }
}
```

!> 不推荐

```js
export default {
  name: 'app',
  data () {
    return {
    }
  },
  methods: {
    getData () {
      let name = 'qui'


      console.log(name)
    }
  }
}
```

`统一使用ES6/7等语法`

```js
1. let const
2. 解构赋值
3. 模板字符串
4. 箭头函数
5. 异步变成使用async await
6. 使用扩展符
7. 模块化开发
8. 使用class定义类和继承
```
```js
*ESLint规则:
"no-var": 0,//禁用var，用let和const代替
"prefer-destructuring": ["error", {
      "array": true,  //数组解构
      "object": true  //对象解构
    }, {
      "enforceForRenamedProperties": false  //决定 object 解构是否应用于重命名的变量
    }
]
"allowNamedFunctions": false //禁止使用命名的函数作为回调函数或函数参数
"allowUnboundThis": true  //允许包含 this 的函数表达式被用作回调函数，只要问题函数没有被显式绑定

```
`对象属性是函数时省掉function关键字`
```js
*ESLint规则:
"object-shorthand": ["error", "always"] //对象中的方法和属性总是使用简写形式
```

> 正确示例

```js
let obj = {
  getName () {
    
  }
}
```

!> 不推荐

```js
let obj = {
  getName: functon() {
    
  }
}
```

`对象属性和外部变量名相同时使用简写`
```js
*ESLint规则:  同上
```
> 正确示例

```js
let name = 'qui'
let obj = {
  title: '主页',
  name
}
```

!> 不推荐

```
let name = 'qui'
let obj = {
  title: '主页',
  name: name
}
```

`普通函数使用小驼峰，构造函数使用大驼峰`
```js
*ESLint规则:
"new-cap": [2, {
    "newIsCap": true,
    "capIsNew": false
}], // 构造函数名字首字母要大写
"camelcase": [2, {
    "properties": "never"
}], // 强制驼峰命名规则
```

```js
// 普通函数
function myFun () {

}

// 构造函数
function MyFun () {

}
```

`创建对象数组时使用字面量方式, 避免使用构造函数`

> 正确示例

```js
let obj = {}
let arr = []
```

!> 不推荐

```js
let obj = new Object()
let arr = new Arrary()
```

### Vue规范

`Vue单文件组件需要声明name属性，使用小驼峰式`

```js
export default {
  name: 'app',
  data () {
    return {

    }
  }
}
```

`尽量的避免使用dom操作，多用状态控制`

`v-for循环时，需要设置key属性，并且保证唯一性`

> 正确示例

```js
<template>
  <div id="app">
    <div v-for="item in dataList" :key="item.id">
      {{ item.name }}
    </div>
  </div>
</template>
```

!> 不推荐
```js
<template>
  <div id="app">
    <div v-for="item in dataList">
      {{ item.name }}
    </div>
  </div>
</template>
```

`vue组件中，定义style样式时，加上作用域属性scoped`

> 正确示例

```css
<style lang="less" scoped>
  .qui-name {
      color: red;
  }
</style>
```
!> 不推荐

```css
<style lang="less">
  .qui-name {
      color: red;
  }
</style>
```

`vue组件之间传递属性时props需要加上验证`

> 正确示例

```js
<script>
export default {
  props: {
    quiName: {
      type: String,
      default: ''
    },
    dataList: {
      type: Array,
      default: () => {
          return []
      }
    }
  }
}
</script>
```

`vue父子组件传递属性时使用小写,多个单词之间加中划线`

> 正确示例

```js
<template>
  <div id="app">
    <my-com :data-list="dataList"></my-com>
  </div>
</template>
```

> 不推荐

```js
<template>
  <div id="app">
    <my-com :dataList="dataList"></my-com>
  </div>
</template>
```