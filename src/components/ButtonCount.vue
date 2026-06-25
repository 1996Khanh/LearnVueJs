<template>
  <button @click="emit('increase')">Increase</button>
  <button @click="callFunctionIncreaseByTwoTimes">Increase by two times</button>
  <button @click="callFunctionIncreaseBy(10, 10)">Increase by</button>
</template>

<script setup>
const emit = defineEmits(['increase', 'increase-by-two-times', 'increase-by'])

const callFunctionIncreaseByTwoTimes = () => {
  emit('increase-by-two-times')
}

const callFunctionIncreaseBy = (number1, number2) => {
  emit('increase-by', number1, number2)
}
</script>
