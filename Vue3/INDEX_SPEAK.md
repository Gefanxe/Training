這裡是為期 5 天的 Vue 3 教育訓練講稿，內容涵蓋基礎到進階，每天分為上午（8:00~12:00）與下午（13:00~17:00）的課程。以下是詳細內容，並附有示例代碼。

---

# **Vue 3 教育訓練講稿**

## **第一天：Vue 3 基礎入門**
### **上午課程：Vue 3 簡介與基本語法**
#### **1. Vue 3 介紹**
- Vue.js 是一個漸進式 JavaScript 框架，專注於 UI 開發。
- Vue 3 相較於 Vue 2，帶來了更好的性能、Composition API 等新特性。

#### **2. 建立 Vue 3 項目**
使用 Vite 建立 Vue 3 項目：
```sh
npm create vite@latest my-vue-app --template vue
cd my-vue-app
npm install
npm run dev
```

#### **3. Vue 基礎語法**
建立一個最簡單的 Vue 應用：
```vue
<script setup>
import { ref } from 'vue';

const message = ref('Hello Vue 3!');
</script>

<template>
  <h1>{{ message }}</h1>
</template>
```

---

### **下午課程：模板語法與指令**
#### **1. 模板語法**
- 插值語法 `{{ }}`
- 屬性綁定 `:attribute`
- 事件綁定 `@event`

示例：
```vue
<template>
  <input :value="message" @input="updateMessage" />
</template>

<script setup>
import { ref } from 'vue';
const message = ref('Hello Vue 3!');

const updateMessage = (event) => {
  message.value = event.target.value;
};
</script>
```

#### **2. Vue 指令**
- `v-if` / `v-else` / `v-show`
- `v-for`
- `v-bind`
- `v-model`

示例：
```vue
<template>
  <p v-if="isVisible">這是一個條件渲染的段落。</p>
  <button @click="isVisible = !isVisible">切換顯示</button>
</template>

<script setup>
import { ref } from 'vue';
const isVisible = ref(true);
</script>
```

---

## **第二天：Vue 3 組件與 Props**
### **上午課程：組件基礎**
#### **1. 建立 Vue 組件**
```vue
<template>
  <h2>我是子組件</h2>
</template>
```
```vue
<template>
  <ChildComponent />
</template>

<script setup>
import ChildComponent from './ChildComponent.vue';
</script>
```

#### **2. Props 傳遞數據**
```vue
<!-- ChildComponent.vue -->
<template>
  <h2>{{ title }}</h2>
</template>

<script setup>
defineProps(['title']);
</script>
```
```vue
<!-- Parent.vue -->
<template>
  <ChildComponent title="這是標題" />
</template>

<script setup>
import ChildComponent from './ChildComponent.vue';
</script>
```

---

### **下午課程：組件事件與插槽**
#### **1. 透過 `$emit` 傳遞事件**
```vue
<!-- Child.vue -->
<template>
  <button @click="$emit('increment')">增加</button>
</template>
```
```vue
<!-- Parent.vue -->
<template>
  <Child @increment="count++" />
  <p>當前計數：{{ count }}</p>
</template>

<script setup>
import { ref } from 'vue';
import Child from './Child.vue';

const count = ref(0);
</script>
```

#### **2. 插槽 Slot**
```vue
<template>
  <slot>預設內容</slot>
</template>
```
```vue
<template>
  <Child>這是插槽內容</Child>
</template>
```

---

## **第三天：Vue 3 的 Composition API**
### **上午課程：Composition API 基礎**
```vue
<script setup>
import { ref } from 'vue';

const count = ref(0);
</script>

<template>
  <button @click="count++">增加</button>
  <p>計數：{{ count }}</p>
</template>
```

---

### **下午課程：`computed` 與 `watch`**
```vue
<script setup>
import { ref, computed } from 'vue';

const count = ref(0);
const doubleCount = computed(() => count.value * 2);
</script>

<template>
  <p>雙倍計數：{{ doubleCount }}</p>
</template>
```

---

## **第四天：Vue 3 路由與狀態管理**
### **上午課程：Vue Router**
安裝 Vue Router：
```sh
npm install vue-router
```

定義路由：
```js
import { createRouter, createWebHistory } from 'vue-router';
import Home from '../views/Home.vue';
import About from '../views/About.vue';

const routes = [
  { path: '/', component: Home },
  { path: '/about', component: About },
];

const router = createRouter({
  history: createWebHistory(),
  routes,
});

export default router;
```

---

### **下午課程：Pinia 狀態管理**
安裝 Pinia：
```sh
npm install pinia
```

定義 Store：
```js
import { defineStore } from 'pinia';

export const useCounterStore = defineStore('counter', {
  state: () => ({ count: 0 }),
  actions: {
    increment() {
      this.count++;
    },
  },
});
```

---

## **第五天：Vue 3 的進階特性**
### **上午課程：Vue 3 的生命週期與異步處理**
```vue
<script setup>
import { onMounted } from 'vue';

onMounted(() => {
  console.log('組件已掛載');
});
</script>
```

---

### **下午課程：組件最佳化與性能調優**
- 使用 `defineAsyncComponent`
- `Suspense` 的使用
- `Teleport` 技術

示例：
```vue
<template>
  <Teleport to="body">
    <div class="modal">這是彈窗</div>
  </Teleport>
</template>
```

---

這是完整的 5 天 Vue 3 課程講稿，每個章節都包含代碼示例，確保學員能夠清楚理解並應用。你覺得這樣的安排如何？有沒有需要調整的地方？