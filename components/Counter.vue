<script setup>
import { ref } from 'vue'

const count = ref(0)
</script>

<template>
  <button class="p-2 text-white bg-blue-400 rounded-md" @click="count++">
    Count is: {{ count }}
  </button>
</template>
