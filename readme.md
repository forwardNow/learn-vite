# learn vite and vue3

>针对熟悉 vue2 的人

## 1. 创建项目

初始化 `vite + vue3 + ts` 项目：

```shell
npm init vite@latest

Need to install the following packages:
  create-vite@latest
Ok to proceed? (y) y

# 项目名称 01-hello-world
√ Project name: ... 01-hello-world

# 使用 vue 框架
√ Select a framework: » vue

# 使用 ts
√ Select a variant: » vue-ts

Scaffolding project in D:\dev\learn\learn-vite\01-hello-world...

Done. Now run:

  cd 01-hello-world
  npm install
  npm run dev

```

安装依赖：

```shell
cd .\01-hello-world\
npm i
```

执行 npm scripts：

```shell
npm run dev
```

打开网址（`http://localhost:3000/`）：

![./assets/images/01.1.helloworld.png](./assets/images/01.1.helloworld.png)

## 创建 vue 实例

vue2: 

```javascript
import Vue from 'vue';
import App from './App.vue';

new Vue({
  render: h => h(App),
}).$mount('#app');
```

vue3: 

```javascript
import { createApp } from 'vue';
import App from './App.vue';

createApp(App).mount('#app');
```

## 多根元素

在 SFC（单文件组件，`*.vue`）中的 `<template>` 中：

* vue2 只能有一个根元素
* vue3 可以有多个根元素

## 选项式 API 和 组合式 API

### 响应式属性 

vue2: 
```javascript
new Vue({
  data() {
    return {
      message: 'hello world!',
    };
  },
}).$mount('#app');
```

vue3:

```vue
<script lang="ts">
import { ref } from 'vue';

export default {
  setup() {
    const name = ref('zhang san');
    const age = ref(18);

    return {
      name,
      age,
    };
  }
};
</script>
<template>
  <div>{{ name }}</div>
  <div>{{ age }}</div>
</template>
```