<script setup>

import '@coreui/coreui/dist/css/coreui.min.css'
import 'bootstrap/dist/css/bootstrap.min.css'

import { useResizeObserver } from '@vueuse/core'
import { ref, watch } from 'vue'

import Dashboard from './pages/dashboard.vue';

const el = ref(null);
const text = ref('');

useResizeObserver(el, (entries) => {
  const [entry] = entries
  const { width, height } = entry.contentRect
  text.value = `width: ${width}\nheight: ${height}`
})

watch(el, text)
</script>

<template>
  <div class="default-background-color" ref="el">
    <NuxtLayout>
      <NuxtPage />
    </NuxtLayout>
  </div>
</template>

<style>
.default-background-color {
  background-color: #f8f9fa;
  min-height: 100vh;
}
</style>
