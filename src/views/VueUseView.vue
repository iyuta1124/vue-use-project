<script setup lang="ts">
import VueUseDemo from '@/components/VueUseDemo.vue'
</script>

<template>
  <div class="vueuse-page">
    <h1>VueUse デモページ</h1>
    <p class="description">
      このページではVueUseライブラリの機能をデモンストレーションしています。
      現在は以下の機能が実装されています：
    </p>
    <ul class="feature-list">
      <li>マウスポインターの位置追跡（usePointer）</li>
      <li>ダークモード切り替え（useDark, useToggle）</li>
    </ul>

    <VueUseDemo />
  </div>
</template>

<style scoped>
.vueuse-page {
  max-width: 1200px;
  margin: 0 auto;
  padding: 2rem;
}

h1 {
  color: var(--color-heading);
  font-size: 2rem;
  margin-bottom: 1rem;
}

.description {
  color: var(--color-text);
  margin-bottom: 1rem;
  line-height: 1.6;
}

.feature-list {
  margin: 1rem 0 2rem;
  padding-left: 1.5rem;
  color: var(--color-text);
}

.feature-list li {
  margin: 0.5rem 0;
  line-height: 1.4;
}
</style>
