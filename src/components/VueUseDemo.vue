<script setup lang="ts">
import { usePointer, useDark, useToggle } from '@vueuse/core'

// マウスの位置を追跡
const { x, y } = usePointer()

// ダークモードの状態管理
const isDark = useDark()
const toggleDark = useToggle(isDark)
</script>

<template>
  <div class="vue-use-demo" :class="{ 'dark-mode': isDark }">
    <h2>VueUse デモ</h2>

    <div class="mouse-tracker">
      <h3>マウスの位置</h3>
      <p>X: {{ Math.round(x) }}, Y: {{ Math.round(y) }}</p>
    </div>

    <div class="theme-switcher">
      <h3>テーマ切り替え</h3>
      <button @click="toggleDark()">
        {{ isDark ? '🌞 ライトモード' : '🌙 ダークモード' }}
      </button>
    </div>
  </div>
</template>

<style scoped>
.vue-use-demo {
  padding: 2rem;
  border-radius: 8px;
  background-color: #ffffff;
  color: #2c3e50;
  transition: all 0.3s ease;
}

.vue-use-demo.dark-mode {
  background-color: #2c3e50;
  color: #ffffff;
}

.mouse-tracker,
.theme-switcher {
  margin: 1rem 0;
  padding: 1rem;
  border: 1px solid #ddd;
  border-radius: 4px;
}

.dark-mode .mouse-tracker,
.dark-mode .theme-switcher {
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

button:hover {
  background-color: #3aa876;
}

.dark-mode button {
  background-color: #64748b;
}

.dark-mode button:hover {
  background-color: #475569;
}
</style>
