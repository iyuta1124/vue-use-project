<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue'

const x = ref(0)
const y = ref(0)

const updateMousePosition = (event: MouseEvent) => {
  x.value = event.clientX
  y.value = event.clientY
}

onMounted(() => {
  window.addEventListener('mousemove', updateMousePosition)
})

onUnmounted(() => {
  window.removeEventListener('mousemove', updateMousePosition)
})
</script>

<template>
  <div class="mouse-tracker">
    <h2>マウストラッカー</h2>
    <div class="position">
      <p>X: {{ Math.round(x) }}, Y: {{ Math.round(y) }}</p>
    </div>
  </div>
</template>

<style scoped>
.mouse-tracker {
  padding: 1rem;
  border: 1px solid #ddd;
  border-radius: 4px;
  background-color: #ffffff;
}

.position {
  margin-top: 1rem;
  font-size: 1.2rem;
  color: #2c3e50;
}
</style>
