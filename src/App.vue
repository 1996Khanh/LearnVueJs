<!-- <script setup>
import { ref } from 'vue'
const text = ref('')

const handleInput = (event) => {
  text.value = event.target.value
}
</script>

<template>
  <p>{{ text }}</p>
  <input :value="text" @input="handleInput" placeholder="Nhập tên của bạn" />
</template> -->

<script setup>
import { ref } from 'vue'
const text = ref('')
</script>

<template>
  <p>{{ text }}</p>
  <input v-model="text" placeholder="Nhập tên của bạn" />
</template>
