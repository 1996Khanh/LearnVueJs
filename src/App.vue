<script setup>
import { ref, watchEffect } from 'vue'

const x = ref(0)
const y = ref(0)

watchEffect(() => {
  console.log(`x=${x.value}, y=${y.value}, tổng=${x.value + y.value}`)
})
</script>

<template>
  <button @click="x++">x++</button>
  <button @click="y++">y++</button>
</template>
