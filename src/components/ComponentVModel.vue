<template>
  <div>
    <input type="text" v-model="username" />
    <p>{{ username }}</p>

    <button @click="setUsernameDefault">Set username default</button>
  </div>
</template>

<script setup>
const [username, modifiers] = defineModel('username', {
  set(value) {
    if (modifiers.capitalize && value) {
      // chỉ chữ đầu hoa, phần còn lại giữ nguyên
      return value.charAt(0).toUpperCase() + value.slice(1)
    }
    return value
  },
})

const setUsernameDefault = () => {
  username.value = 'thaycacac'
}
</script>
