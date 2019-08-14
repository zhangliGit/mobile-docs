
!> 此规范主要规定开发过程中常见的界面处理以及展示方式

### 1. 列表页

`展示列表页，当没有数据时需要使用NoData组件提示暂无数据，不能留空白`

```js
<template>
  <div>
    <no-data v-if="dataList.length === 0"></no-data>
    <div v-for="data in dataList" :key="data">{{ data }}</div>
  </div>
</template>
<script>
  import NoData from '@c/common/NoData'
  export default {
    name: 'home',
    components: {
      NoData
    },
    data () {
      return {
        dataList: [1,2,3]
      }
    }
  }
</script>
```

### 2. 删除或提交操作

`进行删除或提交操作时，要给出弹出确认框提示用户，不要直接操作，删除必须有提示，其他视情况而定`

```js
this.$tools.delTip('您确定删除吗', () => {
  // todo
})
```

### 3. 提交或审批操作

`当用户进行操作时，成功或失败必须给出相应提示，如果需要跳转界面，不能立即跳转，等待1-2s用户看清提示后跳转`

```js
this.$Toast('操作成功')
this.$tools.goNext(() => {
  this.$router.go(-1)
})
```