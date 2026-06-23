<script setup>
import { ref } from 'vue'

const count = ref(0)

const increase = () => count.value++
</script>

<template>
  <p>{{ count }}</p>
  <button @click="increase">Increase</button>
</template>
