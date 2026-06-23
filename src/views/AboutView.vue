<template>
  <div class="about">
    <h1>Count: {{ count }}</h1>
    <button @click="increaseCount">Increase</button>
  </div>
</template>

<script setup>
import { ref, onUpdated, onBeforeUpdate } from 'vue'

const count = ref(0)

const increaseCount = () => {
  count.value++
}

onUpdated(() => {
  console.log('onUpdated')
})

onBeforeUpdate(() => {
  console.log('onBeforeUpdate')
})
</script>
