!> 开发规范是前端团队成员共同探讨以及梳理的结果，开发规范没有统一的标准，不需要多和细，符合自身团队的才是合格的，没有规矩不成方圆，因此每位团队成员都应有责任依照制定的规范编写。

#### 目录结构规范

```
vue
│   
└─── build
|    | 
|    └─── tool.js (多模块打包构建)
└─── src
│    |
│    └─── assets (公用资源目录)
|    |    └─── css (全局样式文件)
|    |    |    └─── global.less (全局公用样式)
|    |    |    └─── qui-base.less (qui基础样式)
|    |    |    └─── vant-reset.less (vant全局样式重写)
|    |    |    └─── variables.less (全局less变量，混合样式)
│    |    └─── image (公用图片)
│    |    └─── js (公用脚本)
|    |    |    └─── vant-plugin (vant注册全局常用组件)
│    └─── components
|    |    └─── common (qui组件，不需要改动)
|    |    └─── custom (项目自定义公用组件)
│    └─── config
|    |    └─── index.js (多环境打包配置)
│    └─── pages
|    |    └─── index (项目入口模块)
|    |    └─── demo (示例模块)
|    |    |    └─── api (api接口)
|    |    |    └─── assets (项目资源目录)
|    |    |    |    └─── css (项目公用样式)
|    |    |    |    └─── img(image)
|    |    |    |    └─── js (项目公用脚本)
|    |    |    └─── component (项目组件)
|    |    |    └─── router (路由配置)
|    |    |    └─── store (vuex配置)
|    |    |    └─── view (路由界面)
|    |    |    └─── utils (项目工具文件)
|    |    |    |    └─── filters.js (项目过滤器)
|    |    |    |    └─── directives.js (项目指令)
|    |    |    |    └─── mixins.js (项目混合)
|    |    |    └─── App.vue (主界面)
|    |    |    └─── mian.js (入口文件)
│    └─── utils
|    |    └─── ajax-serve.js (异步请求封装)
|    |    └─── dirctives.js (全局指令)
|    |    └─── filters.js (全局过滤器)
|    |    └─── mixins.js (全局混合)
|    |    └─── tools.js (全局常用工具函数)
|    |    └─── rem.js (适配方案)
|    |    └─── validate.js (表单验证)
│    └─── vue-config.js (webpack配置)
│    └─── upload.js (项目发布)
```