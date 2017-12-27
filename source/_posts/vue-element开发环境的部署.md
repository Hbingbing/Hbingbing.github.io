---
title: vue+element开发环境的部署
date: 2017-12-20 14:18:02
tags:
- vue
---
### 一、前期准备的开发环境
1. nodejs
2. npm

### 二、搭建 vue 开发环境
1. 安装vue
```
npm install vue
```
2. 安装vue脚手架
```
npm install -g vue-cli
// 等同于
npm install -global vue-cli
```

3. 创建一个基于 webpack 模板的项目文件 my-project
```
vue init webpack my-project
```

4. 进入项目文件
```
cd my-project
```

5. 安装依赖项
```
npm install
```

6. 运行项目
```
npm run dev
```
![](/images/vue.png)

### 三、搭建 element-ui 开发环境
1. 安装 element-ui
```
npm install element-ui
```

2. 在 /src/main.js 中引入 element-ui
```
import ElementUI from 'element-ui'
import 'element-ui/lib/theme-chalk/index.css'

Vue.use(ElementUI)
```

3. 修改 app.vue 为：
```
<template>
  <el-form ref="form" :model="form" label-width="80px">
    <el-form-item label="活动名称">
      <el-input v-model="form.name"></el-input>
    </el-form-item>
    <el-form-item label="活动区域">
      <el-select v-model="form.region" placeholder="请选择活动区域">
        <el-option label="区域一" value="shanghai"></el-option>
        <el-option label="区域二" value="beijing"></el-option>
      </el-select>
    </el-form-item>
    <el-form-item label="活动时间">
      <el-col :span="11">
        <el-date-picker type="date" placeholder="选择日期" v-model="form.date1" style="width: 100%;"></el-date-picker>
      </el-col>
      <el-col class="line" :span="2">-</el-col>
      <el-col :span="11">
        <el-time-picker type="fixed-time" placeholder="选择时间" v-model="form.date2" style="width: 100%;"></el-time-picker>
      </el-col>
    </el-form-item>
    <el-form-item label="即时配送">
      <el-switch v-model="form.delivery"></el-switch>
    </el-form-item>
    <el-form-item label="活动性质">
      <el-checkbox-group v-model="form.type">
        <el-checkbox label="美食/餐厅线上活动" name="type"></el-checkbox>
        <el-checkbox label="地推活动" name="type"></el-checkbox>
        <el-checkbox label="线下主题活动" name="type"></el-checkbox>
        <el-checkbox label="单纯品牌曝光" name="type"></el-checkbox>
      </el-checkbox-group>
    </el-form-item>
    <el-form-item label="特殊资源">
      <el-radio-group v-model="form.resource">
        <el-radio label="线上品牌商赞助"></el-radio>
        <el-radio label="线下场地免费"></el-radio>
      </el-radio-group>
    </el-form-item>
    <el-form-item label="活动形式">
      <el-input type="textarea" v-model="form.desc"></el-input>
    </el-form-item>
    <el-form-item>
      <el-button type="primary" @click="onSubmit">立即创建</el-button>
      <el-button>取消</el-button>
    </el-form-item>
  </el-form>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      form: {
        name: '',
        region: '',
        date1: '',
        date2: '',
        delivery: false,
        type: [],
        resource: '',
        desc: ''
      }
    }
  },
  methods: {
    onSubmit () {
      console.log('submit!')
    }
  }
}
</script>
```
运行结果如下,说明 element-ui 安装成功
![](/images/vue-element.png)

### 四、more
更多 element-ui 组件样式 请前往 [http://element-cn.eleme.io/#/zh-CN](http://element-cn.eleme.io/#/zh-CN)
