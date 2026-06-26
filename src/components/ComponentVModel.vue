<template>
  <div>
    <!-- input email + username ở đây -->
    <input type="text" v-model="email" />
    <p>{{ email }}</p>

    <input type="text" v-model="username" />
    <p>{{ username }}</p>

    <!-- <button @click="setEmailDefault">Set email default</button> -->
    <!-- <button @click="setUsernameDefault">Set username default</button> -->
  </div>
</template>

<script setup>
const email = defineModel()
const username = defineModel('username')

const setEmailDefault = () => {
  email.value = 'thaycacac.official@gmail.com'
}

const setUsernameDefault = () => {
  username.value = 'thaycacac'
}
</script>
