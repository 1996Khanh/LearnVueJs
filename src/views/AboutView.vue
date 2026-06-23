<template>
  <div class="about">
    <h1>Timer: {{ time }}</h1>
  </div>
</template>

<script setup>
import { onBeforeMount, onBeforeUnmount, onMounted, onUnmounted, ref } from 'vue'

const time = ref(0)
const intervalId = ref(null)

onMounted(() => {
  intervalId.value = setInterval(() => {
    time.value++
  }, 1000)
})

onUnmounted(() => {
  clearInterval(intervalId.value)
})

onBeforeMount(() => {
  console.log('onBeforeMount')
})

onBeforeUnmount(() => {
  console.log('onBeforeUnmount')
})
</script>
