<script setup>
const submit = () => {
  alert('Form submitted')
}
</script>

<template>
  <input @keyup.enter.alt="submit" placeholder="Nhập tên của bạn" />
  <button @click.shift="submit">Submit</button>
</template>
