### StepList 审批流程列表

> 描述：审批列出列表

> 用法：`组件`

### NoData 列表无数据时展示

> 描述：列表无数据时展示

> 用法：`组件`

```css
<template>
  <div class="no-data qui-page qui-fx-ver">
    <no-data msg="什么都没有~"></no-data>
  </div>
</template>
<script>
  import NoData from '@c/common/NoData'
  export default {
    components: {
      NoData
    },
    data () {
      return {}
    },
    methods: {
    }
  }
</script>
```
> 属性

名字|类型|是否必需|默认值|说明
:-|:-|:-:|:-:|:-
msg|String|否|提示文本内容
