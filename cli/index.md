### 脚手架

**qui脚手架是基于vue/cli3.0构建的，其在编译和打包性能方面有了很大的提升，而webpack配置方面也更加友好，我们在此模板的基础上进行丰富和优化，形成一套完善的开发模板，开箱即用，不需要额外的配置**


### 全局安装

```
> cnpm i qui-cli -g 
  or
> yarn global install qui-cli
```

### 查看版本

```
> qui-cli -V
```

### 初始化项目

```
> qui-cli init project-name

> cd project-name

> cnpm i
```

### 运行项目

`开发环境`

```
> npm run dev
```

`测试环境`

```
> npm run dev-test
```

`生产环境`

```
> npm run dev-prod
```

!> 环境配置请参考src/assets/config目录下host-env模块文件

### 打包项目 (分模块打包可参考发布流程)

`开发环境`

```
> npm run build
```

`测试环境`

```
> npm run build-test
```

`生产环境`

```
> npm run build-prod
```
