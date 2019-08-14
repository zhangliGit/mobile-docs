###  CalendarShow 日历展示

> 描述：日历展示控件

> 用法：`组件`


```css
<template>
  <div class="calendar-show qui-page qui-fx-ver">
    <calendar-show :exception-list = "exceptionList" :normal-list="normalList" @get-date = "getDate"></calendar-show>
  </div>
</template>
<script>
  import CalendarShow from '@c/common/CalendarShow'
  export default {
    components: {
      CalendarShow
    },
    data () {
      return {
        exceptionList: [1,2,3,4],
        normalList: [11,14,16]
      }
    },
    methods: {
      getDate (date, type) {
        // type： {year: 2019, month: 7, day: 28}
        // type: true 点击头部下一页下一月， false 点击日期
        console.log(date, type)
      }
    }
  }
</script>
```
> 属性

名字|类型|是否必需|默认值|说明
:-|:-|:-:|:-:|:-
exception-list|Array|否|[]|正常日期天数列表
normal-list|Array|否|[]|异常日期天数列表, date为返回日期，type为点击日历的类型

> 事件

名字|参数|说明
:-|:-:|:-
get-date|(date, type)|点击日历触发，


### DateTime 日期时间选择器

> 描述：时间选择器

> 用法：`组件`

> 注意事项：`传递的日期格式为2019/07/10(以斜杠分割)`

```css
<template>
  <div class="calendar-show qui-page qui-fx-ver">
    <date-time :min-date="minDate" :max-date="maxDate" type="datetime" :date="currentDate" v-model="isShow" @get-date = 'getDate'></date-time>
  </div>
</template>
<script>
  import DateTime from '@c/common/DateTime'
  export default {
    components: {
      DateTime
    },
    data () {
      return {
        minDate: '2019/07/10',
        maxDate: '2025/08/10'
        currentDate: '2019/08/14',
        isShow: isShow
      }
    },
    methods: {
      getDate (date) {
        console.log(date)
      }
    }
  }
</script>
```
> 属性

名字|类型|是否必需|默认值|说明
:-|:-|:-:|:-:|:-
v-model|Boolean|是|false|是否显示日期选择框
min-date|String|否|当前日期前10年|最小日期时间
max-date|String|否|当前日期后10年|最大日期时间
type|String|否|datetime|类型 (datetime, date, time, year-month)

> 事件

名字|参数|说明
:-|:-:|:-
get-date|(date)|选择的日期时间