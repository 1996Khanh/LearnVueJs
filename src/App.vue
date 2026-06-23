<script setup>
import { ref } from 'vue'

const isActive = ref(true)
const hasError = ref(true)

const changeActive = () => {
  isActive.value = !isActive.value
}

const changeHasError = () => {
  hasError.value = !hasError.value
}
</script>

<template>
  <button @click="changeActive" class="button" :class="{ active: isActive }">
    {{ isActive ? 'Active' : 'Deactive' }}
  </button>

  <button @click="changeHasError" class="button" :class="{ 'has-error': hasError }">
    {{ hasError ? 'Has Error' : 'No Error' }}
  </button>
</template>

<style>
.button {
  border: none;
  background: #ede9fe;
  color: #8b5cf6;
  padding: 10px 14px;
  border-radius: 6px;
  cursor: pointer;
  &:hover {
    background: #c7d2fe;
  }
}

.active {
  background: #8b5cf6;
  color: white;
  &:hover {
    background: #818cf8;
  }
}

.has-error {
  background: #ef4444;
  color: #fee2e2;
  &:hover {
    background: #f87171;
  }
}
</style>
