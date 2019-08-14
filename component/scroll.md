### ScrollList 界面上下滑动

> 描述：界面区域上下滑动

> 用法：`组件`

> 注意事项：`添加分页数据后，需要调用this.$refs.scrollList.refresh()来刷新控件`

```css
<template>
  <div class="scroll-list qui-page qui-fx-ver">
    <scroll-list ref="scrollList" pullUpLoad @loadMore="loadMore">
      <div class="list qui-bd-b" v-for="i in dataList" :key="i">
        我是第{{i}}条数据
      </div>
    </scroll-list>
  </div>
</template>
<script>
  import ScrollList from '@c/common/ScrollList'
  export default {
    components: {
      ScrollList
    },
    data () {
      return {
        dataList: 20
      }
    },
    methods: {
      loadMore (item) {
        this.dataList += 20
      }
    }
  }
</script>
```
> 属性

名字|类型|是否必需|默认值|说明
:-|:-|:-:|:-:|:-
pullUpLoad|Boolean|否|false|是否开启下拉底部刷新功能

> 事件

名字|参数|说明
:-|:-:|:-
loadMore|-|滑动到界面底部时触发


### LevelScroll 水平滑动

> 描述：水平滑动

> 用法：`组件`

```css
<template>
  <div class="scroll-list qui-page qui-fx-ver">
    <level-scroll>
      <ul class="level-list">
        <li><span>大别山里的一所学校里却充满了孩子爽朗的笑声</span></li>
        <li><span>上海枫叶国际学校目前开设了初中和高中,是否考虑过开设小学</span></li>
        <li><span>近日,济南市教育局、济南市体育局等部门联合印发</span></li>
      </ul>
    </level-scroll>
  </div>
</template>
<script>
  import LevelScroll from '@c/common/LevelScroll'
  export default {
    components: {
      LevelScroll
    },
    data () {
      return {
      }
    },
    methods: {
    }
  }
</script>
<style lang="less" scoped>
  .level-list {
    display: inline-block;
    white-space: nowrap;
    li {
      display: inline-block;
    }
  }
<style>
```
> 属性

名字|类型|是否必需|默认值|说明
:-|:-|:-:|:-:|:-
notice-list|Array|是|[]|通知列表
time|Number|否|3000|滚动间隔
height|Number|否|1.6|滚动区域高度（单位值为rem）

> 事件

名字|参数|说明
:-|:-:|:-
show|item|点击当前公告触发，返回公告项


### NoticeScroll 通知上下滚动

> 描述：通知上下滚动

> 用法：`组件`


```css
<template>
  <div class="scroll-list qui-page qui-fx-ver">
    <notice-scroll @show="show" :notice-list="noticeList"></notice-scroll>
  </div>
</template>
<script>
  import NoticeScroll from '@c/common/NoticeScroll'
  export default {
    components: {
      NoticeScroll
    },
    data () {
      return {
        noticeList: [
          {
            id: 1,
            content: '今天有暴雨'
          },
          {
            id: 2,
            content: '今年五一放假3天'
          },
          {
            id: 3,
            content: '全品文教移动平台上线'
          }
        ]
      }
    },
    methods: {
      show (item) {
        // {id: 3,content: '全品文教移动平台上线'}
        console.log(item)
      }
    }
  }
</script>
```
> 属性

名字|类型|是否必需|默认值|说明
:-|:-|:-:|:-:|:-
notice-list|Array|是|[]|通知列表
time|Number|否|3000|滚动间隔
height|Number|否|1.6|滚动区域高度（单位值为rem）

> 事件

名字|参数|说明
:-|:-:|:-
show|item|点击当前公告触发，返回公告项
