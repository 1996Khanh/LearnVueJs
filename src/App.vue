<script setup>
import { ref } from 'vue'

const text = ref('')
</script>

<template>
  <p>Text: {{ text }}</p>
  <input type="text" v-model.lazy="text" />
  <p>Text: {{ text }}</p>
  <input type="text" v-model.number="text" />
  <p>Text: {{ text }}</p>
  <input type="text" v-model.strim="text" />
</template>
