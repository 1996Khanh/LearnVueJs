<script setup>
import { ref, onMounted, nextTick } from 'vue'

const list = ref(['Item 1', 'Item 2', 'Item 3'])
const itemRefs = ref([])

onMounted(() => {
  nextTick(() => {
    itemRefs.value.forEach((item) => {
      item.style.transition = 'opacity 5s'
      requestAnimationFrame(() => {
        item.style.opacity = '1'
      })
    })
  })
})
</script>

<template>
  <ul>
    <li v-for="(item, index) in list" :key="index" ref="itemRefs" style="opacity: 0">
      {{ item }}
    </li>
  </ul>
</template>
