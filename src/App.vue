<script setup>
import { ref, watch, computed, reactive } from 'vue'

// Ví dụ 1 — Watch một ref cơ bản
// const count = ref(0)
// watch(count, (newVal, oldVal) => {
//   console.log(`Đổi từ ${oldVal} → ${newVal}`)
// })

// Ví dụ 2 — Watch computed
// const x = ref(0)
// const y = ref(0)
// const sum = computed(() => x.value + y.value)
// watch(sum, (newVal, oldVal) => {
//   console.log(`Tổng: ${oldVal} → ${newVal}`)
// })

// Ví dụ 3 — immediate: true (chạy ngay khi load)
// const name = ref('Khanh')
// watch(
//   name,
//   (newVal) => {
//     console.log('Tên hiện tại:', newVal)
//   },
//   { immediate: true }
// )

// Ví dụ 4 — Watch nhiều nguồn cùng lúc
// const firstName = ref('')
// const lastName = ref('')
// watch([firstName, lastName], ([newFirst, newLast]) => {
//   console.log('Họ tên:', newFirst, newLast)
// })

// Ví dụ 5 — Watch một field trong reactive object
const user = reactive({ name: 'Khanh', age: 20 })
watch(
  () => user.age,
  (newAge) => {
    console.log('Tuổi mới:', newAge)
  }
)
</script>

<template>
  <!-- Ví dụ 1 -->
  <!-- <p>{{ count }}</p> -->
  <!-- <button @click="count++">+1</button> -->

  <!-- Ví dụ 2 -->
  <!-- <p>Tổng: {{ sum }}</p> -->
  <!-- <button @click="x++">Tăng x</button> -->
  <!-- <button @click="y++">Tăng y</button> -->

  <!-- Ví dụ 3 -->
  <!-- <input v-model="name" /> -->

  <!-- Ví dụ 4 -->
  <!-- <input v-model="firstName" placeholder="Tên" /> -->
  <!-- <input v-model="lastName" placeholder="Họ" /> -->

  <!-- Ví dụ 5 -->
  <p>{{ user.name }} — {{ user.age }} tuổi</p>
  <button @click="user.age++">Tăng tuổi</button>
</template>
