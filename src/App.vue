<script setup>
import { reactive, computed, ref } from 'vue'

const book = reactive({
  name: 'Book 1',
  chapters: [],
})

const isPublished = computed(() => {
  console.log('function chạy')
  return book.chapters.length > 0 ? 'Có' : 'Không'
})

// const isPublished = () => {
//   console.log('function chạy')
//   return book.chapters.length > 0 ? 'Có' : 'Không'
// }

const addChapter = () => {
  book.chapters.push('Chapter')
}

const count = ref(0)
</script>

<template>
  <div>
    <p>Book name: {{ book.name }}</p>
    <p>Đã xuất bản: {{ isPublished }}</p>
    <button @click="addChapter">Add chapter</button>

    <p>{{ count }}</p>
    <button @click="count++">Click random</button>
  </div>
</template>
