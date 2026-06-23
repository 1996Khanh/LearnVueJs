<script setup>
import { reactive, ref } from 'vue'

const object = reactive({
  count: 2,
  user: {
    age: 18,
  },
  array: [1, 2, 3],
})

const change = () => {
  object.count++
  object.user.age++
  object.array.push(0)
}
</script>

<template>
  <p>{{ object.count }}</p>
  <p>{{ object.user.age }}</p>
  <p>{{ object.array }}</p>
  <button @click="change">Change</button>
</template>
