<script setup>
import { ref, onMounted } from 'vue'

const name = ref('')
const inputRef = ref(null)

onMounted(() => {
  inputRef.value.focus()
})
</script>

<template>
  <input type="text" v-model="name" ref="inputRef" />
</template>
