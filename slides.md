---
theme: seriph
highlighter: shiki
lineNumbers: false
drawings:
  persist: false
css: unocss
title: 前端技术分享
---

# 前端技术分享

<div class="flex justify-center items-center gap-12 text-4xl">
  <div flex="~ col" class="items-center">
    <img class="w-32" src="assets/images/vue.svg" />
    <span>Vue</span>
  </div>
  <span>+</span>
  <div flex="~ col" class="items-center">
    <img class="w-32" src="assets/images/vite.svg" />
    <span>Vite</span>
  </div>
</div>

<div class="absolute bottom-10 right-14">
  <p class="text-right">吴正宏</p>
  <p class="text-right">2022/11/21</p>
</div>

---

# 什么是Vue?

<p v-click>
Vue 是一款用于构建用户界面的 JavaScript 框架。它基于标准 HTML、CSS 和 JavaScript 构建，并提供了一套声明式的、组件化的编程模型，帮助你高效地开发用户界面
</p>

<Counter v-click />

<div grid="~ cols-2 gap-4">
<div v-click>

```html
<button id="btn">Count is: 0</button>
<script>
  let count = 0
  // 拿到目标元素
  const btn = document.getElementById('btn')
  function increment(e) {
    e.target.innerText = `Count is: ${++count}`
  }
  // 绑定点击事件
  btn.addEventListener('click', increment)
</script>
```

</div>
<div v-click>

```vue
<script setup>
import { ref } from 'vue'
// 响应式状态
const count = ref(0)
// 用来修改状态、触发更新的函数
function increment() {
  count.value++
}
</script>

<template>
  <button @click="increment">
    Count is: {{ count }}
  </button>
</template>
```

</div>
</div>

---

# Vue响应式基础

<div grid="~ cols-2 gap-4">
<div v-click>
ref

```vue
<script setup>
import { ref } from 'vue'
// 响应式状态
const count = ref(0)
// 用来修改状态、触发更新的函数
function increment() {
  count.value++
}
</script>

<template>
  <button @click="increment">
    Count is: {{ count }}
  </button>
</template>
```

</div>
<div v-click>
reactive

```vue
<script setup>
import { reactive } from 'vue'
// 响应式状态
const state = reactive({ count: 0 })
// 用来修改状态、触发更新的函数
function increment() {
  state.count++
}
</script>

<template>
  <button @click="increment">
    Count is: {{ state.count }}
  </button>
</template>
```

</div>
</div>

---
layout: center
class: text-center
---

# 谢谢

