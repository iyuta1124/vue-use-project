<script setup lang="ts">
import { useMouse } from '@vueuse/core'

const { x, y } = useMouse()
</script>

<template>
  <div class="vue-use-demo">
    <h2>VueUse デモ</h2>
    <div class="mouse-tracker">
      <h3>マウスの位置</h3>
      <p>X: {{ Math.round(x) }}, Y: {{ Math.round(y) }}</p>
    </div>
  </div>
</template>

<style scoped>
.vue-use-demo {
  height: 100%;
  border-radius: 8px;
  background-color: #ffffff;
  color: #2c3e50;
  transition: all 0.3s ease;
}

.mouse-tracker {
  margin: 1rem 0;
  padding: 1rem;
  border: 1px solid #ddd;
  border-radius: 4px;
  border-color: #4a5568;
}

button {
  padding: 0.5rem 1rem;
  border: none;
  border-radius: 4px;
  background-color: #42b883;
  color: white;
  cursor: pointer;
  transition: background-color 0.3s ease;
}
</style>
