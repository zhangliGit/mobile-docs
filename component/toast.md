### 提示框

> 描述：弹出提示框

> 用法：.alert(params)

> 参数

参数 | 类型 | 是否必需 | 说明
:-|:-|:-|:-
params | Object | 是 | 弹出框参数

> 示例

```
this.$loading.alert({
  content: '提交成功',
  onHide () {
    // 点击确定按钮回调
  }
})
```