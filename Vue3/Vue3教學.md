# Vue 3 Composition API 教學計畫（5 天）

## 簡介

本課程涵蓋 Vue 3 Composition API 的基礎與進階應用，適合想要學習 Vue 3 現代開發方式的開發者。每天的內容包含理論、實作範例和最佳實踐。

<div style="page-break-before: always"></div>

## **第一天：Vue 3 簡介與 Composition API 基礎**

### 1. Vue 3 概述

- Vue.js 發展歷史與核心概念
- Vue 3 相較於 Vue 2 的改變
- Composition API 與 Options API 的比較

### 2. 安裝與設定

- 使用 Vite 建立 Vue 3 專案
- Vue SFC (單文件組件) 結構介紹

### 3. Composition API 基礎

- `setup` 函數的作用
- `ref` 和 `reactive` 創建響應式狀態

#### 範例：

```html
<script setup>
import { ref, reactive } from 'vue';

const count = ref(0);
const user = reactive({ name: 'Alice', age: 25 });
</script>
```

### 4. 討論與練習

- 嘗試將 `ref` 和 `reactive` 應用於簡單的計數器或表單輸入。

<div style="page-break-before: always"></div>

## **第二天：計算屬性與監聽**

### 1. 計算屬性 (Computed Properties)

- 使用 `computed` 來建立派生數據
- `computed` vs `methods`

#### 範例：

```html
<script setup>
import { ref, computed } from 'vue';

const price = ref(100);
const quantity = ref(2);
const total = computed(() => price.value * quantity.value);
</script>
```

### 2. 監聽器 (Watch 和 WatchEffect)

- `watch` 用於監視單個或多個值變化
- `watchEffect` 自動收集依賴

#### 範例：

```html
<script setup>
import { ref, watch } from 'vue';

const message = ref('Hello');
watch(message, (newVal, oldVal) => {
  console.log(`Message changed from ${oldVal} to ${newVal}`);
});
</script>
```

### 3. 討論與練習

- 嘗試監聽一個響應式物件並在變更時執行動作。

<div style="page-break-before: always"></div>

## **第三天：生命周期與模板引用**

### 1. Vue 3 生命周期

- Vue 2 vs Vue 3 的生命周期對照
- `onMounted`, `onUpdated`, `onUnmounted` 等鉤子函數

#### 範例：

```html
<script setup>
import { ref, onMounted } from 'vue';

const message = ref('載入中...');
onMounted(() => {
  setTimeout(() => {
    message.value = '載入完成！';
  }, 2000);
});
</script>
```

### 2. 模板引用 (`ref` 與 DOM 操作)

- `ref` 與 `template ref` 的搭配使用

#### 範例：

```html
<script setup>
import { ref, onMounted } from 'vue';

const inputRef = ref(null);
onMounted(() => {
  inputRef.value.focus();
});
</script>

<template>
  <input ref="inputRef" placeholder="自動獲得焦點" />
</template>
```

### 3. 討論與練習

- 使用生命周期鉤子來實現倒數計時。

<div style="page-break-before: always"></div>

## **第四天：依賴注入與狀態管理**

### 1. 依賴注入 (`provide` / `inject`)

- 作用範圍與用法
- 父組件提供數據，子組件獲取數據

#### 範例：

```html
<!-- Parent.vue -->
<script setup>
import { ref, provide } from 'vue';

const theme = ref('dark');
provide('theme', theme);
</script>
```

```html
<!-- Child.vue -->
<script setup>
import { inject } from 'vue';

const theme = inject('theme');
</script>

<template>
  <p>目前主題：{{ theme }}</p>
</template>
```

### 2. Pinia 狀態管理 (Vuex 替代方案)

- 安裝與設定
- 創建 Store
- 讀取與更新狀態

#### 範例：

```javascript
// store.js
import { defineStore } from 'pinia';
export const useCounterStore = defineStore('counter', {
  state: () => ({ count: 0 }),
  actions: {
    increment() { this.count++; }
  }
});
```

### 3. 討論與練習

- 嘗試使用 Pinia 建立一個待辦事項應用。

<div style="page-break-before: always"></div>

## **第五天：錯誤處理、最佳實踐與優化**

### 1. Vue 3 中的錯誤處理

- `try/catch` 與異步操作
- Vue 全局錯誤處理

#### 範例：

```html
<script setup>
import { ref } from 'vue';

const fetchData = async () => {
  try {
    let response = await fetch('https://api.example.com/data');
    let data = await response.json();
    console.log(data);
  } catch (error) {
    console.error('發生錯誤：', error);
  }
};
</script>
```

### 2. 組件優化與性能提升

- 避免不必要的 re-render
- `defineProps` 與 `defineEmits` 最佳實踐
- `v-memo` 與 `v-once` 的使用

### 3. 最佳實踐與 Q&A

- 組件拆分策略
- 組合式函數 (Composables) 如何組織
- 常見錯誤與解決方案

<div style="page-break-before: always"></div>

## 結語

本課程提供了完整的 Vue 3 Composition API 介紹，透過理論與實作相結合，幫助開發者掌握 Vue 3 現代開發方式。

