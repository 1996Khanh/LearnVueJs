<script setup>
const submit = () => {
  alert('Form submitted')
}

const sayHi1 = () => {
  alert('say hi 1')
}

const sayHi2 = () => {
  alert('say hi 2')
}
</script>

<template>
  <button @click.self="sayHi1">
    <button @click.self="sayHi2">say hi 2</button>
    say hi 1
  </button>
  <form @submit.prevent="submit">
    <button type="submit">Submit</button>
  </form>
</template>
