<script setup>
const num = 2

const isButtonDisabled = false

const listString = 'a,b,c,d,e,f,g,h,i,j'

const convertToId = (data) => data.split(',').reverse().join('-')
</script>

<template>
  <button>{{ num * 2 }}</button>
  <br />
  <br />
  <button :disabled="isButtonDisabled">
    {{ isButtonDisabled ? 'Disabled' : 'Click here' }}
  </button>
  <br />
  <br />
  <button :id="convertToId(listString)">click here 2</button>
</template>
