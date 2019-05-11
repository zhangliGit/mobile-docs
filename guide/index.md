### Qui简介

Qui是武汉全品前端团队根据自身产品制定的一个移动端开发框架体系，基于vue/cli3.0和webpack4.x构建，前端技术栈为vue+vuex+vue-router+qui+webpack+es6/7+less，旨在帮助前端团队成员减少沟通成本，提高开发效率，更加统一的完成产品开发，主要包括如下部分：

> Qui架手架

qui脚手架是基于vue/cli3.0构建的，其在编译和打包性能方面有了很大的提升，而webpack配置方面也更加友好，我们在此模板的基础上进行丰富和优化，形成一套完善的开发模板，开箱即用，不需要额外的配置

> Qui组件库

 qui组件库是根据公司移动端产品规范设计的一套ui组件，能帮助开发人员更加高效的进行界面开发，同时也保证产品风格的统一性

> Qui工具库

 虽然目前有很多开源工具库，功能也非常强大，但是去使用总会感觉有点臃肿，往往用到的功能非常少，而移动端也非常注重应用的性能和体验，所有团队根据自身的产品封装了一套常用的JavaScript工具函数库，以到达性能最优化

> 开发规范

 开发规范是项目开发的基石，如果没有规范，每个成员按照自己的书写习惯进行模块开发，这无疑会造成团队协作和后续的维护成本，甚至会出现很多意想不到的bug，因此团队成员通过沟通讨论之后制定了一套开发规范

> 开发流程

 开发流程在前后端分离模式下尤为重要，项目开发过程中会经历各种节点，涉及到产品需求，前端，后端，测试等，如果某一个环节事先没有处理好，遗留的问题会随着项目的推进无限放大，造成人力成本的大大浪费，所有我们也制定了一套流程规范，提前熟知我们该做的事情，确保项目按照正常的流程节点有序推进

> 发布流程

 发布流程作为项目的最后一步，虽然没有大的工作量，但也非常重要，复杂的项目往往涉及多个环境和服务，如果靠人工切换打包环境和服务，难免会有疏忽，因此团队制定了一套发布流程的规范，避免犯错，同时也提高发布效率

### 布局适配

针对移动端不同分辨率设备的布局，我们选用最新的css3伸缩盒子模型Flex，此模型相比传统布局可以说是为移动端而生的，非常适合自适应式布局，为了方便书写以及统一性，团队基于Flex的相关属性封装了一套基础布局样式库

+ 弹性布局

```html
<div class="qui-fx">
    <div class="box"></div>
</div>
```

+ 水平居中

```html
<div class="qui-fx-jc">
    <div class="box"></div>
</div>
```
+ 水平居右

```html
<div class="qui-fx-je">
    <div class="box"></div>
</div>
```
+ 水平两端对齐

```html
<div class="qui-fx-jsb">
    <div class="box"></div>
    <div class="box"></div>
</div>
```

+ 水平等间距对齐

```html
<div class="qui-fx-jsa">
    <div class="box"></div>
    <div class="box"></div>
</div>
```

+ 垂直居中

```html
<div class="qui-fx-ac">
    <div class="box"></div>
</div>
```

+ 垂直居下

```html
<div class="qui-fx-ae">
    <div class="box"></div>
</div>
```

+ 元素水平垂直居中

```html
<div class="qui-fx-ac-jc">
    <div class="box"></div>
    <div class="box"></div>
</div>
```

+ 元素水平布局可换行

```html
<div class="qui-fx-wp">
    <div class="box"></div>
    <div class="box"></div>
    <div class="box"></div>
    <div class="box"></div>
    <div class="box"></div>
</div>
```

+ 元素一等分

```html
<div class="qui-fx">
    <div class="box"></div>
    <div class="qui-fx-f1"></div>
</div>
```
### 字体单位适配

开发时UI效果图以 750*1334 为标准，界面字体使用js动态设置（默认750 * 1334设为20px），css单位值使用postcss-plugin-px2rem插件动态转换px为rem值，开发时只要测量效果图实际px值即可（相关配置已在项目模板中完成，开发时不必理会）

```js
// 例如UI中有个区域的大小为 120*120px， 则直接写为对应的值，不需要手动转化
.box {
    width: 100px;
    height: 100px;
    background-color: red
}
// 编译后会自动转化为 (375*667)
.box {
    width: 2.5rem;
    height: 2.5rem;
    baackground-color: red
}
```
!> 如果不希望px值被转为rem，则可以大写单位值 width: 100PX

### 图标库

根据产品和UI组件库中常用的图标，基于iconfont整理了一套图标库, 相比图片文件体积更小使用更加方便