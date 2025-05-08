<script setup lang="ts">
import { ref } from 'vue'
import VueUseDemo from './components/VueUseDemo.vue'
import MouseTracker from './components/MouseTracker.vue'

const currentComponent = ref<'vueuse' | 'custom'>('vueuse')

const options = [
  { value: 'vueuse', label: 'VueUse実装' },
  { value: 'custom', label: 'カスタム実装' },
]
</script>

<template>
  <main>
    <div class="controls">
      <select v-model="currentComponent" class="component-select">
        <option v-for="option in options" :key="option.value" :value="option.value">
          {{ option.label }}
        </option>
      </select>
    </div>

    <div class="component-container">
      <VueUseDemo v-if="currentComponent === 'vueuse'" />
      <MouseTracker v-else />
    </div>
  </main>
</template>

<style scoped>
main {
  padding: 2rem;
}

.controls {
  margin-bottom: 2rem;
  text-align: center;
}

.component-select {
  padding: 0.5rem 1rem;
  border: 1px solid #ddd;
  border-radius: 4px;
  background-color: white;
  font-size: 1rem;
  cursor: pointer;
  min-width: 200px;
}

.component-select:focus {
  outline: none;
  border-color: #42b883;
}

.component-container {
  max-width: 600px;
  margin: 0 auto;
}
</style>
