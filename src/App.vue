<script setup>
import { ref, watch } from 'vue'

const question = ref('')
const isLoading = ref(false)
const answer = ref('')
// const count = ref(0)

// const increaseCount = () => {
//   count.value++
// }

// watch(count, (newVal, oldVal) => {
//   console.log(`newVal: ${newVal}, oldVal: ${oldVal}`)
// })
watch(question, async (newQuestion) => {
  if (newQuestion.includes('?')) {
    isLoading.value = true
    answer.value = 'Đang suy nghĩ...'
    try {
      const response = await fetch('https://yesno.wtf/api')
      answer.value = (await response.json()).answer
    } catch (error) {
      answer.value = 'Error! Không thể call api'
    } finally {
      isLoading.value = false
    }
  }
})
</script>

<template>
  <!-- <p>{{ count }}</p>
  <button @click="count++">Increase</button> -->

  <div>
    <input v-model="question" :disabled="isLoading" />
    <p>{{ answer }}</p>
  </div>
</template>
