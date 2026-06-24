<script setup>
import { ref } from 'vue'

const props = defineProps({
  init: Number,
})

const count = ref(props.init)
</script>
<template>
  <button @click="count++">{{ count }}</button>
</template>
