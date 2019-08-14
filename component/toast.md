

### comfirm 确认框

> 描述：在删除操作或需要操作提示的时候调用

> 示例：`js`

```js
  this.$tools.delTip('确定删除吗?', () => {
    // todo
  })

```

> 示例：`组件`

### actionsheet 底部弹出框

> 描述：actionsheet底部弹出菜单框

> 示例：`组件`

```css
<template>
  <div class="select-data qui-page qui-fx-ver">
    <action-sheet title="选择菜单" :action-list="actionList" v-model="isShow" @select="select"></action-sheet>
    <div class="select-list qui-fx-ac qui-fx-jsb qui-bd-b">
      <div>选择菜单：</div>
      <div @click="isShow = true" class="qui-fx-f1 qui-tx-r" style="color:#666">{{ type }}</div>
      <div class="rit-icon"></div>
    </div>
  </div>
</template>
<script>
  import ActionSheet from '@c/common/ActionSheet'
  export default {
    components: {
      ActionSheet
    },
    data () {
      return {
        isShow: false,
        type: '请选择',
        actionList: [
          {
            id: '1',
            name: '年假'
          },
          {
            id: '2',
            name: '事假'
          },
          {
            id: '3',
            name: '婚假'
          }
        ]
      }
    },
    methods: {
      confirm (item) {
        this.type = item.name
      }
    }
  }
</script>
```
> 属性

名字|类型|是否必需|默认值|说明
:-|:-|:-:|:-:|:-
v-model|Boolean|是|false|slect弹出框显示状态
title|String|否|请选择|弹出框标题
action-list|Array|是||底部菜单列表

> 事件

名字|参数|说明
:-|:-:|:-
select|-|点击菜单时触发，返回当前项菜单对象


### PopupBox 弹出信息展示

> 描述：弹出层信息展示（弹出框公用）

> 示例：`组件`

```css
<template>
  <popup-box v-model="isShow" @confirm="isShow = false"  width="80" height="80">
    <div class="info-list">
        <div style="height: 2rem; line-height: 2rem;" class="qui-bd-b" v-for="i in 20" :key="i">
          {{ i }}
        </div>
    </div>
  </popup-box>
</template>
<script>
  import PopupBox from '@c/common/PopupBox'
  export default {
    components: {
      PopupBox
    },
    data () {
      return {
        isShow: false
      }
    },
    methods: {
    }
  }
</script>
```
> 属性

名字|类型|是否必需|默认值|说明
:-|:-|:-:|:-:|:-
v-model|Boolean|是|false|弹出层显示状态
width|String|否|80|弹出层宽度 默认80%
height|String|否|80|弹出层高度 默认80%
cancle-text|String|否|''|是否显示取消按钮，以及显示的文字
confirm-text|String|否|确定|确定按钮显示的文字
is-radius|Boolean|否|true|弹出框是否有圆角

> 事件

名字|参数|说明
:-|:-:|:-
confirm|-|点击确认按钮时触发
cancel|-|点击取消按钮时触发

### SelectData 底部选择框

> 描述：select底部选择框

> 示例：`组件`

```css
<template>
  <div class="select-data qui-page qui-fx-ver">
    <select-data title="请假类型" :select-list="selectList" v-model="isShow" @confirm="confirm"></select-data>
    <div class="select-list qui-fx-ac qui-fx-jsb qui-bd-b">
      <div>请假类型：</div>
      <div @click="isShow = true" class="qui-fx-f1 qui-tx-r" style="color:#666">{{ type }}</div>
      <div class="rit-icon"></div>
    </div>
  </div>
</template>
<script>
  import SelectData from '@c/common/SelectData'
  export default {
    components: {
      SelectData
    },
    data () {
      return {
        isShow: false,
        type: '请选择',
        selectList: [
          {
            id: '1',
            text: '年假'
          },
          {
            id: '2',
            text: '事假'
          },
          {
            id: '3',
            text: '婚假'
          }
        ]
      }
    },
    methods: {
      confirm (item) {
        console.log(item)
        this.type = item.text
      }
    }
  }
</script>
```
> 属性

名字|类型|是否必需|默认值|说明
:-|:-|:-:|:-:|:-
v-model|Boolean|是|false|slect弹出框显示状态
title|String|否|请选择|弹出框标题
select-list|Array|是||数据类型列表
> 事件

名字|参数|说明
:-|:-:|:-
confirm|-|点击确认按钮时触发，返回当前项列表对象
